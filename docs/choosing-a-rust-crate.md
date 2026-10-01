# Choosing the right Rust crate

Rust's ecosystem is unusually rich — and unusually churny. A crate that was the
obvious pick two years ago may be passively maintained today. Evaluate candidates
on these signals before committing.

## Maintenance signals

1. **Commit recency and issue responsiveness.** Check the repo's commit graph and how fast maintainers respond to issues/PRs. A year of silence on a networking crate is a red flag; on a stable serialization format, less so.
2. **`unsafe` audit surface.** Prefer crates that minimize `unsafe`, document why each block exists, and run Miri in CI. For security-critical picks (TLS, crypto), prefer crates with audited cores (`rustls`, `ring`/`aws-lc-rs`).
3. **MSRV policy.** Libraries with a stated MSRV (and CI enforcing it) are safer dependencies than ones that casually require the latest nightly.
4. **Dependency weight.** `cargo tree` and `cargo deny` tell you what you're really pulling in. A "tiny" crate dragging in 200 transitive dependencies is a supply-chain and compile-time cost.
5. **Backing and bus factor.** Single-maintainer crates can be excellent — but check whether there's a team, company, or foundation behind critical infrastructure, and whether maintenance has visibly transferred before.

## The async question

Rust ships no async runtime; the ecosystem standardized (mostly) on **Tokio**.
If a crate is Tokio-only and your project uses another executor, check for
`async-std`/`smol` compatibility or runtime-agnostic design. For new projects,
Tokio-first is the path of least resistance.

## Web frameworks

- **axum** is the current default recommendation for new HTTP services: Tokio-native, maintained by the Tokio team, macro-light.
- **actix-web** remains powerful and fast but has had a rockier maintenance history; evaluate its current state before adopting.
- **rocket** prioritizes ergonomics and type-safe routing; check its release cadence against your needs.

## Databases

- Prefer **compile-time checked** query crates (`sqlx` with `query!`) when correctness matters; accept the longer compile times.
- **diesel** (query builder, sync-first) vs **sea-orm** (async entity framework) vs **sqlx** (async, raw-SQL-first): pick by whether you want an ORM, a builder, or SQL with guardrails — not by hype.
- For embedded/local use, SQLite via `rusqlite` and pure-Rust options like `redb` cover most needs.

## Cryptography: don't roll your own

Use `rustls` for TLS, `ring` or `aws-lc-rs` for primitives, and the `RustCrypto` crates (`sha2`, `aes-gcm`, `argon2`…) for standard algorithms. Never hand-roll crypto, and never pick a crypto crate without checking its audit history.

## GUI and games

Both spaces are still maturing. **egui** (immediate-mode) and **iced** (Elm-inspired) lead GUI; **bevy** leads games. Expect API churn; pin versions and read changelogs.

## Quick checklist

- [ ] License confirmed from the repo's LICENSE file or `Cargo.toml`
- [ ] Last commit within a timeframe appropriate to the crate's stability
- [ ] Open issues/PRs getting maintainer responses
- [ ] `unsafe` usage documented or minimal
- [ ] MSRV compatible with your toolchain
- [ ] Dependency tree reviewed (`cargo tree`, `cargo deny`)
