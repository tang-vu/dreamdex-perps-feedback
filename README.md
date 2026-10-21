# dreamDEX Perps Feedback

Seven issue-specific reports/candidates, proposed severity normal. No submission, acceptance or reward is established by this package.

- [001: Perps entry redirects signed-out visitors to spot](feedback/001-perps-entry-opens-spot.md): actual Edge/HTTP observations.
- [002: existing-position bracket side](feedback/002-existing-position-bracket-side.md): explicit offline synthetic source-code reproduction.
- [003: new-entry budget blocks existing-position management](feedback/003-existing-position-entry-preflight.md): explicit offline synthetic source-code reproduction.
- [004: named maximum position permits a near-cap quote beyond it](feedback/004-maker-position-cap-semantics.md): reproduced offline behavior; strict-vs-soft cap intent requires clarification, so lower confidence as a malfunction.
- [005: skipped quotes are not retried at an unchanged mark](feedback/005-maker-skipped-quote-retry.md): explicit offline synthetic source-code reproduction.

- [006: cancellation errors lose quote tracking](feedback/006-maker-cancel-failure-loses-tracking.md): explicit offline failure injection; related public issue 38 is disclosed, so duplicate risk is higher.
- [007: SDK createOrder misses the distinct perp minimum](feedback/007-sdk-create-order-minimum.md): actual public BTC grid plus 12 offline cases in SDK 0.32.1.

Reports 002-006 concern the official bot kit, not claimed markets-sdk library defects. Report 007 concerns the SDK unified adapter's local validation. Bot-kit eligibility, duplicates and severity are for the organizer to decide. No real account, trade, fill, stop, exposure or financial loss is asserted by their test fixtures.

With Node 24:

```powershell
node feedback/repro/001-perps-entry-redirect.mjs
node --experimental-vm-modules feedback/repro/002-existing-position-side.mjs
node --experimental-vm-modules feedback/repro/003-existing-position-preflight.mjs
node --experimental-vm-modules feedback/repro/004-maker-position-limit.mjs
node --experimental-vm-modules feedback/repro/005-maker-skipped-quote-retry.mjs
node --experimental-vm-modules feedback/repro/006-maker-cancel-failure.mjs
```

Keep the adjacent shared helpers. The offline tests retrieve pinned public source, verify hashes and run original function bodies with explicit test doubles. Only 003-006 replace the startup footer for controlled invocation. Reports 001-006 need no dependency installation. 006 uses explicitly labelled in-memory helper-return IDs and an isolated cancellation error seam; none is a live order or receipt. No wallet, key, signature or transaction is needed. See each report for controls and limitations. First-report priority is unknown.

Report 007 uses the original installed SDK method and grid helpers. Install only its pinned public dependencies (Node 24):

```powershell
npm ci --ignore-scripts --no-audit --no-fund
npm run repro:007
```

The minimal package/lock is for this reproducer, not a trading app. Its clean install and all 12 cases were checked in a separate directory. No exchange constructor is run; the prototype-backed test context creates no network connection, owner, signer, transaction or receipt. Its public on-chain configuration observation is separate from its offline fixtures. The npm archive integrity and source hashes are recorded in the report. No acceptance or reward is claimed for any item.
