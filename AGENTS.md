# greet pilot

This repository is an isolated omp-build 0.19.0 pilot, not plugin source.

- Use Bun 1.4.4. Run `bun install --frozen-lockfile`, `bun run lint`, and the applicable behavior tests.
- The preparation commit contains no CLI implementation. The feature UW must implement `greet Alice` producing exactly `Hello, Alice!` with a trailing newline, add consumer-visible tests, and make CI execute those tests.
- The baseline CI validates tooling only. Do not present it as feature verification.
- Use the official native `/feature init` preview and operator-approval procedure for tracker initialization. Do not hand-create its generated contract or labels.
- Use the existing session and `/move`; do not launch another OMP session.
- Respect principal-checkout, confirmation, review, CI, and landing refusals. No manual substitutes for native authority.
- Do not modify Roxabi/roxabi-plugins, its tooling pin, the installed pilot plugin, or issue #951.
