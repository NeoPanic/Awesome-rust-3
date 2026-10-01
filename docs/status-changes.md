# Status changes

Renames, archival notices, deprecations, and license gotchas discovered while
researching this list (verified 2026-09-30). This is the running log — new
entries get appended, not rewritten.

## Renames / moves

- **rocket** — repo moved from `SergioBenitez/Rocket` to `rwf2/Rocket`; crates.io now points at the new org.
- **rg3d → fyrox** — the game engine renamed; listed as fyrox.
- **ratatui** — the maintained fork lineage of the archived `tui-rs` (`ratatui/ratatui`).
- **wasm-pack** — repo moved into the `wasm-bindgen` org (`wasm-bindgen/wasm-pack`).
- **godot-rust → gdext** — current Godot 4 bindings are the `godot` crate from `godot-rust/gdext`; the old `godot-rust` crate targeted Godot 3.

## Archived / deprecated (excluded from the list)

- **viz** — project discontinued; the viz.rs domain and `viz-rs` GitHub org were repurposed for an unrelated "visual creative space" product (discovered 2026-10-01 during final validation — the crates.io page still points at the dead repo).
- **bincode** — upstream `bincode-org/bincode` archived Aug 2025; carries RUSTSEC-2025-0141 (unmaintained). Ecosystem moved to forks or `postcard` (listed).
- **async-std** — deprecated by its own maintainers in favor of `smol` (listed).
- **tui-rs** — repo archived; succeeded by `ratatui` (listed).
- **druid** — discontinued by maintainers; succeeded by `xilem` (listed).
- **amethyst** — repo archived.
- **tide** — dormant; 0.17 beta never released.
- **sled** — perpetual alpha; ecosystem moved to `redb` (listed).
- **cargo-watch** — repo archived Jan 2025; its own README recommends `bacon` or `watchexec` (both listed).
- **piston**, **quicksilver** — dormant/inactive game frameworks.

## License gotchas

- **surrealdb — BSL-1.1.** Business Source License: source-available, *not* OSI open source. Confirmed from the repo LICENSE file.
- **slint — GPL-3.0-only OR LicenseRef-Slint-Royalty-free-2.0 OR LicenseRef-Slint-Software-3.0.** Triple-licensed: GPL-3.0-only, a royalty-free option with attribution, or paid commercial. Not permissive.
- **godot (gdext) — MPL-2.0.** Unusual for this list but confirmed; file-level copyleft.
- **wasmtime — Apache-2.0 WITH LLVM-exception.** Confirmed verbatim.
- **ring — Apache-2.0 AND ISC.** ISC for new files, Apache-2.0 for BoringSSL-sourced files, per its LICENSE.
- **aws-lc-rs — ISC AND (Apache-2.0 OR ISC).** Recorded verbatim from crates.io.
- **redis (crate) — BSD-3-Clause** per crates.io 1.7.1 and its LICENSE text. (This is the Redis *client* crate, not the database server, whose licensing changed separately.)
- **viz — MIT OR Apache-2.0.** crates.io declares MIT, but the repo ships both LICENSE-MIT and LICENSE-APACHE.
- **gotham — MIT OR Apache-2.0.** crates.io's nonstandard `MIT/Apache-2.0` separator normalized.

## Maintenance watch (listed, with caveats)

- **warp** — not archived, but low activity (0.4.3; last push 2026-07-28). Listed for completeness; prefer axum for new services.
- **notan** — author describes it as "slow maintenance mode" in the README.
- **expect-test** — stable but low-churn (last commit 2024-12-21); rust-analyzer's internal snapshot-testing library. Trimmed from the list for scope; `insta` (listed) is the actively developed alternative.
- **tracing** — still 0.1.x (0.1.44); no 1.0 release as of 2026-09-30.
- **dioxus** — latest crates.io release is a prerelease (0.8.0-alpha.1); latest stable is 0.7.x.

## Version notes

- **hyper 1.x** (1.11.1) is current; 0.14 is legacy.
- **bevy 0.19** stable (Jun 2026); 0.20 in RC as of 2026-09-28.
- **tauri v2** stable since 2024-10-02 (2.12.1 on 2026-09-30); Android/iOS first-class since v2.0.
- **rustls** stable is 0.23.x (`Apache-2.0 OR ISC OR MIT`).
- **criterion** 0.8.2, actively maintained through Sep 2026.
- **cargo-audit** 0.22.2, alive in the RustSec org (earlier maintenance transition resolved).
- **actix-web 4.15.0 and axum 0.8.9** both pushed 2026-09-30 — both actively maintained; neither is deprecated.
