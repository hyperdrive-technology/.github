# Contributing to Hyperdrive

Humans and coding agents are welcome. Contributions follow the same process and
review gates. Please follow the [code of conduct](CODE_OF_CONDUCT.md).

## Choose a repository and set up locally

| Repository | Setup and checks |
| --- | --- |
| [core](https://github.com/hyperdrive-technology/core) (private for now) | [README](https://github.com/hyperdrive-technology/core/blob/main/README.md), [CONTRIBUTING](https://github.com/hyperdrive-technology/core/blob/main/CONTRIBUTING.md), [TESTING](https://github.com/hyperdrive-technology/core/blob/main/TESTING.md) |
| [holodeck](https://github.com/hyperdrive-technology/holodeck) | [README](https://github.com/hyperdrive-technology/holodeck/blob/main/README.md), [CONTRIBUTING](https://github.com/hyperdrive-technology/holodeck/blob/main/CONTRIBUTING.md), [Blender guide](https://github.com/hyperdrive-technology/holodeck/blob/main/blender/README.md) |
| [holodeck-sdk](https://github.com/hyperdrive-technology/holodeck-sdk) | [README](https://github.com/hyperdrive-technology/holodeck-sdk/blob/main/README.md), [CONTRIBUTING](https://github.com/hyperdrive-technology/holodeck-sdk/blob/main/CONTRIBUTING.md) |

Use Node 26 and pnpm. Core also needs Rust stable, with the
`wasm32-unknown-unknown` target for M1 work. Holodeck currently depends on a
sibling `holodeck-sdk` checkout through `file:` dependencies; build the SDK
before installing its consumers. Follow the chosen repository's guide for
exact commands and CI checks.

## Contribution flow

1. Search existing issues and PRs. Use a bug, feature or task form in the
   affected repository; ask in Discussions for help choosing work. Discuss
   larger changes in an issue before implementing them.
2. Link the issue and describe your intended approach. Work on a feature branch
   in your fork or, if you have write access, in the repository.
3. Keep the change focused. Add regression tests for bug fixes and tests for
   new behaviour. Update relevant docs and run the repository's checks.
4. Open a PR against the agreed base branch. Use a short imperative or
   conventional-commit title. Explain the problem, resulting behaviour, and how
   you tested it. Include `Closes #N` for the issue being resolved and
   before/after screenshots for UI changes.
5. Address review findings and let CI and both reviews pass on the latest head
   commit. Maintainers squash-merge; merged branches are automatically deleted.

Core's current development base is `feat/brewery-extensions` (PR
[#24](https://github.com/hyperdrive-technology/core/pull/24) into `main`), as of
2026-10-14. Follow the issue's base-branch guidance while that PR is open.
Holodeck and the SDK normally target `main`.

## Review gate

Before merge, CI must be green and both commit statuses must pass on the PR's
current head:

- `claude-review`: independent Claude Code review.
- `gpt-review/sol-6.1`: Codex GPT Sol 6.1 review.

Maintainers arrange and record these reviews. A blocking review must be fixed
and repeated; changes to the head commit require fresh reviews. Holodeck and
the SDK enforce these gates with rulesets; core follows the same process.

## Milestones and tracking

The current milestone is **M1 — Brewery on WASM**: the browser brewery demo must
use the real Rust runtime compiled to WASM and consume Holodeck as built
packages. No TypeScript interpreter, mocks, shims or fallbacks may remain in the
M1 demo path. Test doubles outside that path remain useful for isolated tests.
**M2 — Holodeck standalone scene builder** follows; core's native runtime track
is post-M1. See the [org profile](profile/README.md) for milestone links.

GitHub issues track contribution work. Core's canonical backlog is
[.agents/TODO.md](https://github.com/hyperdrive-technology/core/blob/feat/brewery-extensions/.agents/TODO.md).

Maintainers apply labels during triage. An issue form's area selection records
the requested area; it does not automatically apply a label.

| Label | Meaning |
| --- | --- |
| `area:runtime`, `area:compiler`, `area:wasm`, `area:ui`, `area:holodeck`, `area:sdk`, `area:ci`, `area:docs` | Area affected |
| `priority:p0`, `priority:p1`, `priority:p2` | Priority, highest first |
| `status:blocked` | Waiting on a dependency or decision |
| `needs-des` | Needs a maintainer decision |
| `agent` | Work being done by a coding agent |
| `review-finding` | Follow-up from a review |
| `good first issue` | Suitable for a newcomer |
| `help wanted` | Contributions requested |

Use [SUPPORT.md](SUPPORT.md) for questions and [SECURITY.md](SECURITY.md) for
vulnerabilities. Maintainer: [@DezLitz](https://github.com/DezLitz).
