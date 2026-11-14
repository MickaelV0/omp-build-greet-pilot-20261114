# omp-build greet pilot

Private, isolated preparation repository for omp-build 0.19.0. No UW has been created or started.

## Pilot objective

Implement a small `greet` CLI: `greet Alice` prints exactly `Hello, Alice!` followed by a newline and exits successfully.

The CLI is deliberately not implemented in this preparation commit. Its UW must add executable behavior tests and run them in CI. The initial CI checks tooling and formatting only; a green baseline is not evidence of the greeting behavior. `bun run test` selects Bun's real test runner and currently has no test files.

## Tooling

- Bun 1.4.4, dependency versions locked in `bun.lock`.
- `bun install --frozen-lockfile` installs the development tools.
- `bun run lint` checks formatting and lint rules.
- GitHub Actions use immutable action commits and read-only contents permission.
- `OMP_BUILD_TOOLING_SHA` on this repository pins Roxabi/roxabi-plugins commit `97217aecf672aaeb5ec074a13f72266cb074c991`, carrying omp-build 0.19.0. The source repository and its pin are unchanged.

## Official initialization boundary

Use the existing OMP session and `/move` to the linked `-setup` checkout, not a second OMP process. Run `/feature init` for the official preview. It proposes the test command and tracker contract/labels without applying them. Apply only with the digest from that preview and a genuine operator reply using `/feature init --approve <digest> --operator-approval '<operator reply>'`.

Init application refuses a principal checkout. Do not override that refusal; the linked setup worktree exists for this reason. Commit and publish approved initialization changes before starting the feature. Do not call worktree bootstrap separately: the native feature lifecycle owns it.

The official preview was executed with the installed script and its documented script-directory cwd. It identified this repository but withheld the tracker with `issue-triage missing (... Cannot detect GitHub repo. Set GITHUB_REPO env var or ensure git remote "origin" is configured.)`. No approval was supplied and no tracker contract, labels, or UW were written. Do not approve that incomplete plan or use its digest. Resolve the official initialization path before requesting a fresh native preview; the plugin and session environment have not been patched.

## Known hosting blocker

GitHub Free refuses branch protection for this private repository (HTTP 403), and `allow_auto_merge` remains false. Native landing is not ready. Keep the repository private; upgrade the hosting plan or resolve capabilities explicitly before delivery. Do not replace native landing with a manual merge, loosen checks, or bypass an engine refusal.
