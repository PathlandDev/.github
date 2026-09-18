# PathlandDev

> An open UI protocol — declarative UI, written in your backend. No JavaScript.

[![CI](https://github.com/PathlandDev/Pathland/actions/workflows/ci.yml/badge.svg)](https://github.com/PathlandDev/Pathland/actions/workflows/ci.yml)

**Status: proof of concept.** It works end to end and the tests are green, but the
wire format and APIs may change before 1.0.

We're building **Pathland**: a protocol-first, cross-language UI protocol. You
write the **whole UI in your backend language** — Java, Rust, anything — and
Pathland renders the first page as server-side HTML (instant, SEO-friendly), then
keeps it alive with tiny binary updates over a WebSocket. The result is a smooth,
reactive UI delivered by the backend team — no npm, no bundlers, no separate
frontend.

## What we build

- **A binary UI protocol** — view declarations compile to fixed 16-byte opcodes
  any renderer can apply, so the wire is language- and renderer-agnostic.
- **SwiftUI-shaped DSLs** — `VStack`, `Text`, `Button`, styling — written on the
  backend, right next to your business logic.
- **Native renderers** — the browser DOM (SSR + live WebSocket deltas) today,
  plus a native GTK4 desktop renderer. WASM in the browser, embedded chips, and
  mobile/desktop are the roadmap.
- **Only changes travel** — an unchanged screen transmits zero bytes; updates are
  tiny binary deltas applied in place.

## Repositories

| Repository | Description |
|------------|-------------|
| [Pathland](https://github.com/PathlandDev/Pathland) | The protocol spec, Rust core, Java DSL + Spring/Quarkus starters, renderers, and demos |

More surface is on the way — embedded, WASM, mobile, and desktop targets all speak
the same protocol.

## Try it

Each demo has a one-command launcher in [`Pathland/scripts/`](https://github.com/PathlandDev/Pathland/tree/main/scripts):

| Demo | Command |
|------|---------|
| Spring Boot SSR + WebSocket | `./scripts/run-spring-demo.sh` |
| Quarkus SSR + WebSocket (hot reload) | `./scripts/run-quarkus-demo.sh` |
| Rust DSL → GTK4 desktop renderer | `./scripts/run-rust-gtk-demo.sh` |
| Java DSL → GTK4 desktop renderer | `./scripts/run-java-gtk-demo.sh` |

## Get involved

- [Contributing](https://github.com/PathlandDev/Pathland/blob/main/CONTRIBUTING.md) ·
  [Code of Conduct](https://github.com/PathlandDev/Pathland/blob/main/CODE_OF_CONDUCT.md) ·
  [Security](https://github.com/PathlandDev/Pathland/blob/main/SECURITY.md)
- Browse the [protocol spec](https://github.com/PathlandDev/Pathland/tree/main/spec) —
  `OPCODE.md` is the wire format, `DSL.md` the authoring surface.
- Licensed under [Apache-2.0](https://github.com/PathlandDev/Pathland/blob/main/LICENSE).
Notes:
- The CI badge points to PathlandDev/Pathland (the repo README still has an old michaelkrog/… badge — worth updating there too, if you want).
- The org already has a description set ("Building open-source, binary-first UI protocols…") — it stays next to the README on the profile.
- The .github repo is currently empty, so this will be its first commit.
