# dreamDEX Perps Feedback

Two independent reports, proposed severity normal. No submission, acceptance or reward is established by this package.

- [001: documented Perps entry redirects signed-out visitors to spot](feedback/001-perps-entry-opens-spot.md). Real Edge screenshots and public HTTP responses; authenticated behavior/root cause unverified.
- [002: starter dry-run selects the configured bracket side for an opposite existing position](feedback/002-existing-position-bracket-side.md). Explicitly **offline synthetic** source-code reproduction, not live account, trade, stop or financial-impact evidence. Bot-kit track eligibility is for the organizer to decide.

No wallet, key, signature or trade is needed. Reports include duplicate-check limits; first-report priority is unknown.

With Node 24, run:

```powershell
node feedback/repro/001-perps-entry-redirect.mjs
node --experimental-vm-modules feedback/repro/002-existing-position-side.mjs
```

The second helper retrieves two immutable public source files, verifies their hashes and runs the unchanged strategy/helper logic with clearly labelled test doubles. Both use built-in Node APIs only. See each report for full steps and limitations.
