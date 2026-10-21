# dreamDEX Perps Feedback

Five issue-specific reports/candidates, proposed severity normal. No submission, acceptance or reward is established by this package.

- [001: Perps entry redirects signed-out visitors to spot](feedback/001-perps-entry-opens-spot.md): actual Edge/HTTP observations.
- [002: existing-position bracket side](feedback/002-existing-position-bracket-side.md): explicit offline synthetic source-code reproduction.
- [003: new-entry budget blocks existing-position management](feedback/003-existing-position-entry-preflight.md): explicit offline synthetic source-code reproduction.
- [004: named maximum position permits a near-cap quote beyond it](feedback/004-maker-position-cap-semantics.md): reproduced offline behavior; strict-vs-soft cap intent requires clarification, so lower confidence as a malfunction.
- [005: skipped quotes are not retried at an unchanged mark](feedback/005-maker-skipped-quote-retry.md): explicit offline synthetic source-code reproduction.

Reports 002-005 concern the official bot kit, not a claimed markets-sdk library defect. Bot-kit eligibility, duplicates and severity are for the organizer to decide. No real account, trade, fill, stop, exposure or financial loss is asserted by their test fixtures.

With Node 24:

```powershell
node feedback/repro/001-perps-entry-redirect.mjs
node --experimental-vm-modules feedback/repro/002-existing-position-side.mjs
node --experimental-vm-modules feedback/repro/003-existing-position-preflight.mjs
node --experimental-vm-modules feedback/repro/004-maker-position-limit.mjs
node --experimental-vm-modules feedback/repro/005-maker-skipped-quote-retry.mjs
```

Keep the adjacent shared helpers. The offline tests retrieve pinned public source, verify hashes and run original function bodies with explicit test doubles. Only 003-005 replace the startup footer for controlled invocation. No dependency installation, wallet, key, signature or transaction is needed. See each report for controls and limitations. First-report priority is unknown.
