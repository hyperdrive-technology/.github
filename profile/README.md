# Hyperdrive

Hyperdrive is a virtual PLC project: an IEC 61131-3 compiler, a Rust runtime, and
a browser IDE with SCADA views. Holodeck provides browser editors and viewers for
live animated process scenes; its SDK defines the scene format and extension
contracts.

## Repositories

| Repository | What lives there | Access |
| --- | --- | --- |
| [core](https://github.com/hyperdrive-technology/core) | Compiler, Rust runtime, web IDE and SCADA | Private for now |
| [holodeck](https://github.com/hyperdrive-technology/holodeck) | React 2D and 2.5D editors, 3D viewer, Blender part scripts | Public |
| [holodeck-sdk](https://github.com/hyperdrive-technology/holodeck-sdk) | SceneFile schema, ContributionRegistry and extension contracts | Public |

## Project status

As of 2026-10-14, the brewery demo runs on the TypeScript interpreter. The current
milestone, **M1 — Brewery on WASM**, moves it onto the real Rust runtime compiled
to WASM in a browser Worker, with Holodeck consumed as built packages. The M1
demo path must have no TypeScript interpreter, mocks, shims or fallbacks.

Track M1 in [core](https://github.com/hyperdrive-technology/core/milestone/1),
[Holodeck](https://github.com/hyperdrive-technology/holodeck/milestone/1), and the
[SDK](https://github.com/hyperdrive-technology/holodeck-sdk/milestone/1).
Work includes the [WASM runtime](https://github.com/hyperdrive-technology/core/issues/27),
[IR symbols](https://github.com/hyperdrive-technology/core/issues/30),
[Worker host](https://github.com/hyperdrive-technology/core/issues/31),
[package imports](https://github.com/hyperdrive-technology/holodeck/issues/7), and
[registry atomicity](https://github.com/hyperdrive-technology/holodeck-sdk/issues/6).
Core links require repository access.

Next is **M2 — Holodeck standalone scene builder**:
[core](https://github.com/hyperdrive-technology/core/milestone/2),
[Holodeck](https://github.com/hyperdrive-technology/holodeck/milestone/2),
[SDK](https://github.com/hyperdrive-technology/holodeck-sdk/milestone/2).
The [native runtime track](https://github.com/hyperdrive-technology/core/milestone/3)
follows M1.

## Start here

1. Choose a repository and read its README and CONTRIBUTING guide. Local
   development uses Node 26 and pnpm; core also needs Rust stable. Holodeck
   currently needs a sibling SDK checkout.
2. Read the [contribution process](https://github.com/hyperdrive-technology/.github/blob/main/CONTRIBUTING.md). Humans and coding agents
   follow the same CI and review gates.
3. Browse open `good first issue` items in
   [Holodeck](https://github.com/hyperdrive-technology/holodeck/issues?q=is%3Aissue%20is%3Aopen%20label%3A%22good%20first%20issue%22),
   [the SDK](https://github.com/hyperdrive-technology/holodeck-sdk/issues?q=is%3Aissue%20is%3Aopen%20label%3A%22good%20first%20issue%22), or
   [core](https://github.com/hyperdrive-technology/core/issues?q=is%3Aissue%20is%3Aopen%20label%3A%22good%20first%20issue%22)
   if you have access. If none are available, ask in a public repo's Discussions.

See [support](https://github.com/hyperdrive-technology/.github/blob/main/SUPPORT.md), [security reporting](https://github.com/hyperdrive-technology/.github/blob/main/SECURITY.md), and the
[code of conduct](https://github.com/hyperdrive-technology/.github/blob/main/CODE_OF_CONDUCT.md). Maintainer: [@DezLitz](https://github.com/DezLitz).
