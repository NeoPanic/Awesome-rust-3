# Awesome Rust

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Entries](https://img.shields.io/badge/entries-101-blue)](data/rust.json)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

A curated list of the **Rust ecosystem**: web frameworks, async runtimes, networking, databases, serialization, CLI/TUI, GUI, game engines, WebAssembly, embedded, testing, cryptography, and build tooling.

> **Scope:** this list covers the Rust *ecosystem* — crates, frameworks, and developer tools. The language itself, books, courses, and tutorials are out of scope (see exclusions).
> **Honesty policy:** the original 100 entries were checked against official sources as of 2026-09-30; GPUI Kit was checked against its official repository and license on 2026-10-19 — **101/101 verified**. Unverified entries carry a stated reason. Licenses are copied from the project's actual license declaration; the two non-permissive entries (SurrealDB's BSL-1.1, Slint's GPL/commercial dual-license) are flagged in their sections. Machine-readable data lives in [`data/rust.json`](data/rust.json).

## Contents

- [Web Frameworks](#web-frameworks) — 8 entries
- [Async Runtimes & Networking](#async-runtimes--networking) — 8 entries
- [Databases & ORMs](#databases--orms) — 8 entries
- [Serialization](#serialization) — 7 entries
- [CLI & TUI](#cli--tui) — 9 entries
- [GUI](#gui) — 8 entries
- [Game Engines](#game-engines) — 8 entries
- [WebAssembly](#webassembly) — 9 entries
- [Embedded & no_std](#embedded--no_std) — 7 entries
- [Testing, Benchmarking & Observability](#testing-benchmarking--observability) — 9 entries
- [Cryptography](#cryptography) — 7 entries
- [Build Tooling & Developer Experience](#build-tooling--developer-experience) — 13 entries

## Choosing the right crate

New here? Start with the [choosing-a-rust-crate](docs/choosing-a-rust-crate.md) guide (maintenance signals, the async question, per-category picks), the [glossary](docs/glossary.md), and [status-changes](docs/status-changes.md) (renames, archival notices, license gotchas).

## Web Frameworks

HTTP servers, routers, and full frameworks for building APIs and web services — from minimal to batteries-included. (8 entries)

- [actix-web](https://actix.rs) — Web framework built on the actix actor runtime and tokio; long-standing high-throughput pick. *(MIT OR Apache-2.0 · ⭐ 24,850)*
- [axum](https://crates.io/crates/axum) — Ergonomic web framework built on tokio, tower, and hyper, with handler-based routing. *(MIT · ⭐ 27,309)*
- [gotham](https://gotham.rs/) — Web framework built around a router/handler pipeline, maintained by the gotham-rs team. *(MIT OR Apache-2.0 · ⭐ 2,315)*
- [poem](https://crates.io/crates/poem) — Full-featured web framework with built-in OpenAPI support via poem-openapi. *(MIT OR Apache-2.0 · ⭐ 4,443)*
- [rocket](https://rocket.rs) — Web framework emphasizing type-safe routing, request guards, and fairings; 0.5+ is the stable line. *(MIT OR Apache-2.0 · ⭐ 25,782)*
- [salvo](https://salvo.rs) — Web framework with handler-tree routing; actively maintained. *(Apache-2.0 · ⭐ 4,434)*
- [trillium](https://crates.io/crates/trillium) — Modular, composable toolkit for building async web apps; handler/harness model. *(MIT OR Apache-2.0 · ⭐ 377)*
- [warp](https://crates.io/crates/warp) — Composable filter-based web framework on hyper/tokio; low upstream activity in recent years. *(MIT · ⭐ 10,374)*

## Async Runtimes & Networking

The async foundation: executors, HTTP clients and servers, gRPC, and QUIC. Most of the ecosystem standardizes on Tokio. (8 entries)

- [hyper](https://hyper.rs) — Low-level HTTP/1 and HTTP/2 library (1.x is current); underpins reqwest, axum, and tonic. *(MIT · ⭐ 16,341)*
- [mio](https://crates.io/crates/mio) — Lightweight non-blocking I/O primitives; the polling layer under tokio. *(MIT · ⭐ 7,109)*
- [quinn](https://crates.io/crates/quinn) — Versatile QUIC transport protocol implementation in async Rust. *(MIT OR Apache-2.0 · ⭐ 5,277)*
- [reqwest](https://crates.io/crates/reqwest) — High-level async HTTP client built on hyper; the default HTTP client for most Rust apps. *(MIT OR Apache-2.0 · ⭐ 11,851)*
- [reqwest-middleware](https://crates.io/crates/reqwest-middleware) — Middleware-chain wrapper around reqwest (retry, tracing, etc.). *(MIT OR Apache-2.0 · ⭐ 381)*
- [smol](https://crates.io/crates/smol) — Small, fast async runtime; the officially recommended successor to async-std. *(Apache-2.0 OR MIT · ⭐ 5,082)*
- [tokio](https://tokio.rs) — Event-driven, non-blocking I/O platform; the dominant async runtime for Rust. *(MIT · ⭐ 33,290)*
- [tonic](https://crates.io/crates/tonic) — gRPC over HTTP/2 implementation focused on performance and interoperability. *(MIT · ⭐ 12,486)*

## Databases & ORMs

From compile-time-checked SQL to embedded engines and multi-model databases. Note: SurrealDB is BSL-1.1 source-available, not OSI open source — the only non-OSI entry in this section. (8 entries)

- [diesel](https://diesel.rs) — Safe, extensible ORM and query builder; synchronous with compile-time checks; PostgreSQL, SQLite, MySQL. *(MIT OR Apache-2.0 · ⭐ 14,189)*
- [mongodb](https://www.mongodb.com/docs/drivers/rust/) — The official MongoDB driver for Rust (async). *(Apache-2.0 · ⭐ 1,517)*
- [redb](https://www.redb.org) — Simple, portable, embedded key-value database written in pure Rust. *(MIT OR Apache-2.0 · ⭐ 4,816)*
- [redis](https://crates.io/crates/redis) — Redis client driver for Rust, with async and sync APIs. *(BSD-3-Clause · ⭐ 4,258)*
- [rusqlite](https://crates.io/crates/rusqlite) — Ergonomic bindings for SQLite, with bundled or system SQLite. *(MIT · ⭐ 4,420)*
- [sea-orm](https://www.sea-ql.org/SeaORM) — Async, dynamic ORM built on sqlx with an entity/codegen-first workflow. *(MIT OR Apache-2.0 · ⭐ 9,908)*
- [sqlx](https://crates.io/crates/sqlx) — Async SQL toolkit with compile-time checked queries and no DSL; PostgreSQL, MySQL, SQLite. *(MIT OR Apache-2.0 · ⭐ 17,515)*
- [surrealdb](https://surrealdb.com) — Distributed document-graph database; usable embedded or over remote protocols via the Rust SDK. *(BSL-1.1 · ⭐ 33,086)*

## Serialization

Structs to bytes and back: JSON, MessagePack, CBOR, Protocol Buffers, and Rust-native formats. (7 entries)

- [ciborium](https://crates.io/crates/ciborium) — CBOR (RFC 8949) binary format implementation for serde. *(Apache-2.0 · ⭐ 392)*
- [postcard](https://crates.io/crates/postcard) — Compact no_std-compatible binary format for serde; the maintained bincode alternative. *(MIT OR Apache-2.0 · ⭐ 1,536)*
- [prost](https://crates.io/crates/prost) — Protocol Buffers implementation for Rust, with prost-build codegen. *(Apache-2.0 · ⭐ 4,775)*
- [rmp-serde](https://crates.io/crates/rmp-serde) — MessagePack binary format support for serde. *(MIT · ⭐ 1,425)*
- [ron](https://crates.io/crates/ron) — Rusty Object Notation: a human-readable config file format for serde. *(MIT OR Apache-2.0 · ⭐ 4,023)*
- [serde](https://serde.rs) — Generic serialization/deserialization framework; the ecosystem standard every other entry plugs into. *(MIT OR Apache-2.0 · ⭐ 10,851)*
- [serde_json](https://crates.io/crates/serde_json) — JSON serialization for serde; the default human-readable data format. *(MIT OR Apache-2.0 · ⭐ 5,639)*

## CLI & TUI

Argument parsing, terminal UIs, progress bars, prompts, and terminal styling for command-line apps. (9 entries)

- [clap](https://crates.io/crates/clap) — Full-featured command-line argument parser for Rust. *(MIT OR Apache-2.0 · ⭐ 16,735)*
- [comfy-table](https://crates.io/crates/comfy-table) — Library for building formatted terminal tables with automatic content wrapping. *(MIT · ⭐ 1,403)*
- [console](https://crates.io/crates/console) — Terminal and console abstraction for Rust (colors, input, ANSI handling). *(MIT · ⭐ 1,197)*
- [crossterm](https://crates.io/crates/crossterm) — Cross-platform terminal manipulation library: cursor, styling, events, raw mode. *(MIT · ⭐ 4,236)*
- [dialoguer](https://crates.io/crates/dialoguer) — Command-line prompting library: confirmations, selections, and inputs. *(MIT · ⭐ 1,617)*
- [indicatif](https://crates.io/crates/indicatif) — Progress bars and command-line reporting for Rust. *(MIT · ⭐ 5,218)*
- [inquire](https://crates.io/crates/inquire) — Library for building interactive terminal prompts. *(MIT · ⭐ 2,633)*
- [owo-colors](https://crates.io/crates/owo-colors) — Zero-allocation terminal colors and text styling. *(MIT · ⭐ 810)*
- [ratatui](https://ratatui.rs) — Library for building rich terminal user interfaces and dashboards. *(MIT · ⭐ 22,815)*

## GUI

Desktop GUI toolkits: immediate-mode, Elm-inspired, web-tech (Tauri), and native. Note: Slint is GPL-3.0-only or commercial — the only non-permissive license in this section. (8 entries)

- [egui](https://www.egui.rs) — Easy-to-use immediate-mode GUI library for native and web. *(MIT OR Apache-2.0 · ⭐ 30,771)*
- [gpui](https://gpui.rs) — Zed's GPU-accelerated, hybrid immediate/retained-mode UI framework. *(Apache-2.0 · ⭐ 91,137)*
- [gpui-kit](https://crates.io/crates/gpui-kit) — Component library and umbrella crate for desktop applications built with GPUI. *(Apache-2.0 · ⭐ 18,217)*
- [iced](https://iced.rs) — Cross-platform GUI library inspired by Elm. *(MIT · ⭐ 31,631)*
- [makepad-widgets](https://makepad.dev) — Widget library for Makepad, a cross-platform UI runtime for native and web targets. *(MIT OR Apache-2.0 · ⭐ 7,110)*
- [slint](https://slint.rs) — Declarative GUI toolkit for desktop and embedded; GPL-3.0-only, royalty-free, or commercial license. *(GPL-3.0-only OR commercial · ⭐ 24,027)*
- [tauri](https://tauri.app/) — Framework for building small, secure desktop and mobile apps with a Rust backend and web frontend. *(Apache-2.0 OR MIT · ⭐ 111,510)*
- [xilem](https://xilem.dev) — Next-generation cross-platform UI framework from Linebender (Druid's successor). *(Apache-2.0 · ⭐ 5,540)*

## Game Engines

2D/3D game engines and frameworks, from batteries-included (Bevy) to minimalist (macroquad). (8 entries)

- [bevy](https://bevy.org) — Data-driven game engine and app framework built on ECS. *(MIT OR Apache-2.0 · ⭐ 48,516)*
- [fyrox](https://fyrox.rs) — Feature-rich 2D/3D game engine with a visual scene editor (formerly rg3d). *(MIT · ⭐ 9,571)*
- [ggez](https://ggez.rs) — Lightweight 2D game framework inspired by LOVE. *(MIT · ⭐ 4,698)*
- [godot](https://godot-rust.github.io) — Rust bindings for the Godot 4 game engine (gdext). *(MPL-2.0 · ⭐ 5,241)*
- [macroquad](https://crates.io/crates/macroquad) — Simple, fast-compiling 2D/3D game and graphics library. *(MIT OR Apache-2.0 · ⭐ 4,643)*
- [nannou](https://crates.io/crates/nannou) — Creative-coding framework for generative art and interactive visuals. *(MIT OR Apache-2.0 · ⭐ 6,762)*
- [notan](https://crates.io/crates/notan) — Portable multimedia layer for building games and apps without platform-specific code. *(MIT OR Apache-2.0 · ⭐ 970)*
- [tetra](https://crates.io/crates/tetra) — Simple 2D game framework inspired by LÖVE. *(MIT · ⭐ 1,011)*

## WebAssembly

Compile Rust to WASM, run WASM outside the browser, and build browser apps with Rust frameworks. (9 entries)

- [dioxus](https://dioxuslabs.com) — Full-stack framework for web, desktop, and mobile from a single Rust codebase. *(MIT OR Apache-2.0 · ⭐ 39,304)*
- [gloo](https://gloo-rs.web.app/) — Modular toolkit of utilities for Rust and WebAssembly. *(MIT OR Apache-2.0 · ⭐ 2,000)*
- [leptos](https://leptos.dev/) — Full-stack isomorphic web framework with fine-grained reactivity (signals, SSR). *(MIT · ⭐ 21,343)*
- [trunk](https://crates.io/crates/trunk) — WASM web application bundler: build, bundle, and ship Rust apps to the web. *(MIT/Apache-2.0 · ⭐ 4,398)*
- [wasm-bindgen](https://wasm-bindgen.github.io/wasm-bindgen) — Tooling for JS/Rust interop: import JavaScript into Rust and expose Rust to JavaScript. *(MIT OR Apache-2.0 · ⭐ 9,172)*
- [wasm-pack](https://crates.io/crates/wasm-pack) — Build tool for assembling Rust-generated WebAssembly packages for the web. *(MIT OR Apache-2.0 · ⭐ 7,283)*
- [wasmer](https://wasmer.io/) — WebAssembly runtime for running Wasm on servers, edge, and embedded. *(MIT · ⭐ 21,109)*
- [wasmtime](https://wasmtime.dev) — Standalone WebAssembly runtime from the Bytecode Alliance. *(Apache-2.0 WITH LLVM-exception · ⭐ 18,674)*
- [yew](https://yew.rs) — Component-based web framework with a React-like model and virtual DOM. *(MIT OR Apache-2.0 · ⭐ 32,821)*

## Embedded & no_std

Bare-metal Rust: async executors, hardware abstraction layers, and debug/probe tooling for microcontrollers. (7 entries)

- [cortex-m](https://crates.io/crates/cortex-m) — Low-level access to Cortex-M processors (interrupts, peripherals, registers). *(MIT OR Apache-2.0 · ⭐ 1,008)*
- [defmt](https://knurling.ferrous-systems.com/) — Highly efficient logging framework for resource-constrained devices. *(MIT OR Apache-2.0 · ⭐ 1,234)*
- [embassy](https://embassy.dev) — Async embedded framework for Rust, shipped as modular embassy-* crates (executor, drivers, networking). *(MIT OR Apache-2.0 · ⭐ 9,895)*
- [embedded-hal](https://crates.io/crates/embedded-hal) — Hardware abstraction traits for embedded systems (GPIO, SPI, I2C, UART, and more). *(MIT OR Apache-2.0 · ⭐ 2,656)*
- [esp-hal](https://docs.espressif.com/projects/rust/esp-hal/latest/) — Espressif's officially supported no_std hardware abstraction layer for ESP32 chips. *(MIT OR Apache-2.0 · ⭐ 2,128)*
- [probe-rs](https://crates.io/crates/probe-rs) — On-chip debugging toolkit: flashing, RTT logging, and GDB support for microcontrollers. *(MIT OR Apache-2.0 · ⭐ 2,956)*
- [rtic](https://rtic.rs/) — Real-time interrupt-driven concurrency framework for building real-time systems. *(MIT OR Apache-2.0 · ⭐ 2,411)*

## Testing, Benchmarking & Observability

Prove it works and watch it run: test frameworks, property testing, benchmarks, tracing, and metrics. (9 entries)

- [criterion](https://criterion-rs.github.io/book/index.html) — Statistics-driven micro-benchmarking library; the standard Rust benchmarking tool. *(Apache-2.0 OR MIT · ⭐ 464)*
- [divan](https://crates.io/crates/divan) — Statistically-rigorous benchmarking library that works without nightly features. *(MIT OR Apache-2.0 · ⭐ 1,453)*
- [insta](https://insta.rs/) — Snapshot testing library for Rust, with inline and file-based snapshots. *(Apache-2.0 · ⭐ 2,970)*
- [metrics](https://crates.io/crates/metrics) — Lightweight metrics facade for counters, gauges, and histograms. *(MIT · ⭐ 1,487)*
- [opentelemetry](https://crates.io/crates/opentelemetry) — OpenTelemetry API and SDK for Rust (traces, metrics, logs). *(Apache-2.0 · ⭐ 2,723)*
- [proptest](https://crates.io/crates/proptest) — Property-based testing with automatic shrinking, modeled on Hypothesis. *(MIT OR Apache-2.0 · ⭐ 2,246)*
- [rstest](https://crates.io/crates/rstest) — Fixture-based testing framework with fixtures and parametrized (table-driven) tests. *(MIT OR Apache-2.0 · ⭐ 1,588)*
- [tracing](https://docs.rs/tracing) — Application-level tracing framework for Rust (spans, events, structured logging). *(MIT · ⭐ 6,897)*
- [tracing-subscriber](https://docs.rs/tracing-subscriber) — Utilities for building and composing tracing subscribers (fmt, env-filter, journald, etc.). *(MIT · ⭐ 6,897)*

## Cryptography

TLS and crypto primitives from audited implementations — never roll your own. (7 entries)

- [argon2](https://crates.io/crates/argon2) — Pure-Rust Argon2 password hashing with Argon2d/i/id variants. *(MIT OR Apache-2.0 · ⭐ 911)*
- [aws-lc-rs](https://crates.io/crates/aws-lc-rs) — AWS-maintained, ring API-compatible crypto library backed by AWS-LC. *(ISC AND (Apache-2.0 OR ISC) · ⭐ 655)*
- [chacha20poly1305](https://crates.io/crates/chacha20poly1305) — Pure-Rust ChaCha20-Poly1305 AEAD (RFC 8439), including XChaCha20-Poly1305. *(Apache-2.0 OR MIT · ⭐ 966)*
- [orion](https://crates.io/crates/orion) — High-level, misuse-resistant pure-Rust cryptography (AEAD, hashing, KDF, signatures). *(MIT · ⭐ 723)*
- [ring](https://crates.io/crates/ring) — High-performance crypto primitives built on a BoringSSL-derived core. *(Apache-2.0 AND ISC · ⭐ 4,110)*
- [rustls](https://crates.io/crates/rustls) — Modern pure-Rust TLS implementation; the default TLS backend in reqwest and other clients. *(Apache-2.0 OR ISC OR MIT · ⭐ 7,648)*
- [sha2](https://crates.io/crates/sha2) — Pure-Rust implementation of the SHA-2 hash function family. *(MIT OR Apache-2.0 · ⭐ 2,268)*

## Build Tooling & Developer Experience

Cargo plugins and dev tools: faster test runs, auditing, linting, caching, and file watching. (13 entries)

- [bacon](https://crates.io/crates/bacon) — Background Rust compiler that watches files and shows diagnostics on the fly. *(AGPL-3.0 · ⭐ 3,434)*
- [cargo-audit](https://rustsec.org) — Audits Cargo.lock against the RustSec advisory database for known vulnerabilities. *(Apache-2.0 OR MIT · ⭐ 1,958)*
- [cargo-deny](https://crates.io/crates/cargo-deny) — Cargo plugin for managing dependency graphs: license, advisory, source, and ban checks. *(MIT OR Apache-2.0 · ⭐ 2,436)*
- [cargo-edit](https://crates.io/crates/cargo-edit) — Cargo commands for modifying Cargo.toml: cargo add, rm, upgrade. *(Apache-2.0 OR MIT · ⭐ 3,456)*
- [cargo-expand](https://crates.io/crates/cargo-expand) — Shows the result of macro and derive expansion, wrapping rustc -Zunpretty=expanded. *(MIT OR Apache-2.0 · ⭐ 3,130)*
- [cargo-machete](https://crates.io/crates/cargo-machete) — Fast unused-dependency finder based on AST analysis of your code. *(MIT · ⭐ 1,381)*
- [cargo-nextest](https://crates.io/crates/cargo-nextest) — Next-generation test runner for Rust with per-test results and smarter execution. *(Apache-2.0 OR MIT · ⭐ 3,311)*
- [cargo-outdated](https://crates.io/crates/cargo-outdated) — Cargo subcommand for displaying when dependencies are out of date. *(MIT · ⭐ 1,422)*
- [cargo-udeps](https://crates.io/crates/cargo-udeps) — Finds unused dependencies declared in Cargo.toml. *(MIT OR Apache-2.0 · ⭐ 2,138)*
- [clippy](https://github.com/rust-lang/rust-clippy) — Official Rust linter for catching common mistakes (ships with rustup as cargo clippy); part of the Rust project. *(MIT OR Apache-2.0 · ⭐ 13,548)*
- [rust-analyzer](https://rust-analyzer.github.io/) — Official Rust language server providing IDE intelligence (completions, diagnostics, refactorings). *(MIT OR Apache-2.0 · ⭐ 16,891)*
- [sccache](https://crates.io/crates/sccache) — ccache-like compiler wrapper with local and remote (cloud) caching. *(Apache-2.0 · ⭐ 7,720)*
- [watchexec-cli](https://watchexec.github.io) — Executes commands in response to file modifications; the maintained successor path to cargo-watch. *(Apache-2.0 · ⭐ 7,209)*

## Notable exclusions

Candidates that were researched and deliberately left out:

| Excluded | Reason |
| --- | --- |
| viz | Project discontinued; viz.rs domain and viz-rs GitHub org repurposed for an unrelated product. |
| bincode | Upstream repo archived Aug 2025 (RUSTSEC-2025-0141); ecosystem moved to forks or postcard (listed). |
| async-std | Deprecated by its own maintainers in favor of smol (listed). |
| tide | Dormant; 0.17 beta never released, no commits since Jan 2024. |
| sled | Perpetual alpha; ecosystem moved to redb (listed). |
| tui-rs | Repo archived; succeeded by ratatui (listed). |
| druid | Discontinued by maintainers; succeeded by xilem (listed). |
| amethyst | Repo archived. |
| rg3d | Renamed to fyrox (listed). |
| piston | Dormant. |
| quicksilver | Inactive. |
| cargo-watch | Repo archived Jan 2025; its README points to bacon / watchexec (listed). |
| starship | Shell prompt written in Rust, but not Rust-ecosystem tooling — out of scope. |
| rustup | The toolchain manager; assumed prerequisite, not catalogued. |
| The Rust Book / official learning resources | Language learning material — out of scope for an ecosystem list. |

## Related

More curated lists by the same author:

- [Awesome-terminal](https://github.com/dakotac1994/Awesome-terminal) — terminal emulators and the terminal stack.
- [Awesome-diagram-tool](https://github.com/dakotac1994/Awesome-diagram-tool) — diagramming and visualization tools.
- [Awesome-chrome-extension](https://github.com/dakotac1994/Awesome-chrome-extension) — Chrome/Chromium browser extensions.
- [Awesome-db](https://github.com/dakotac1994/Awesome-db) — database engines by data model.
- [Awesome-python](https://github.com/dakotac1994/Awesome-python) — the general Python ecosystem.
- [awesome-cli](https://github.com/dakotac1994/awesome-cli) — the broad CLI/TUI tools list.
- [awesome-oss-cli](https://github.com/dakotac1994/awesome-oss-cli) — the OSS-only CLI/TUI list.
- [awesome-oss-macos](https://github.com/Awesome-llms-labs/awesome-oss-macos) — open-source macOS apps.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). PRs welcome — every entry must be verified against an official source, with the license copied from the project's actual license declaration.

## License

This list is MIT licensed — see [LICENSE](LICENSE).
