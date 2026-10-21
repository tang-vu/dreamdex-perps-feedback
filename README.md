# dreamDEX Perps Feedback

One reproduced nonsecurity Feedback report: [documented Perps entry redirects signed-out visitors to spot](feedback/001-perps-entry-opens-spot.md). Proposed severity: normal. No submission, acceptance or reward is established by this package.

Evidence includes actual Edge screenshots and public HTTP responses. No wallet, signature or trade was required. Authenticated behavior, root cause and first-report priority remain unverified.

Run `node feedback/repro/001-perps-entry-redirect.mjs` with Node 24 to capture at most three public same-origin GET redirects. No dependencies or credentials are needed. See the report for complete browser reproduction steps and limitations.
