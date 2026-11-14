# omp-build greet pilot

Public, isolated preparation repository for a fictitious omp-build pilot. No UW has been created or started.

## Pilot objective

Implement a small `greet` CLI: `greet Alice` prints exactly `Hello, Alice!` followed by a newline and exits successfully.

The CLI is deliberately not implemented in this preparation commit. Its UW must add executable behavior tests and run them in CI. The initial CI checks tooling and formatting only; a green baseline is not evidence of the greeting behavior. `bun run test` selects Bun's real test runner and currently has no test files.

## Tooling

- Bun 1.4.4, dependency versions locked in `bun.lock`.
- `bun install --frozen-lockfile` installs the development tools. `worktree.setup` declares the same command as a shell snippet for native worktree bootstrap; do not call bootstrap separately.
- `bun run lint` checks formatting and lint rules.
- GitHub Actions use immutable action commits and read-only contents permission.
- The repository variable `OMP_BUILD_TOOLING_SHA` is the authority for the selected Roxabi/roxabi-plugins commit. The principal installation and its pin are separate from this pilot.

## Official initialization boundary

Use the existing OMP session and `/move` to the linked `-setup` checkout, not a second OMP process. Run `/feature init` for the official preview. It proposes the test command and tracker contract/labels without applying them. Never approve a withheld or incomplete plan. Apply only after a complete native preview, with its digest and a separate genuine operator reply using `/feature init --approve <digest> --operator-approval '<operator reply>'`.

Init application refuses a principal checkout. Do not override that refusal; the linked setup worktree exists for this reason. Commit and publish approved initialization changes before starting the feature. Do not call worktree bootstrap separately: the native feature lifecycle owns it.

Do not bypass an incomplete preview, native approval, or any initialization refusal with a manual substitute.

## Hosting and landing

The pilot repository is public. Auto-merge is enabled; merge commits are allowed, while squash and rebase merges are disabled. The `main` branch requires a pull request, the GitHub Actions `Tooling` check with strict up-to-date status, and resolved conversations. Protection applies to administrators and disallows force-pushes and branch deletion; no human approval is required by GitHub.

The `Tooling` check covers the baseline tooling only, not the greeting behavior. Do not replace native landing with a manual merge, loosen checks, or bypass an engine refusal.
