# Glossary

Terms you'll meet constantly in the Rust ecosystem.

- **Crate** — Rust's unit of compilation and distribution: a library or binary package, published on [crates.io](https://crates.io). Roughly "package" in other ecosystems.
- **Cargo** — Rust's build tool and package manager. Handles dependencies, builds, tests, and publishing.
- **Ownership** — Rust's core memory-management discipline: every value has exactly one owner; when the owner goes out of scope, the value is dropped. No garbage collector needed.
- **Borrow checker** — The compiler pass that enforces ownership and borrowing rules at compile time, preventing data races and use-after-free.
- **Borrowing** — Temporarily accessing a value via a reference (`&T` shared, `&mut T` exclusive) without taking ownership.
- **Lifetimes** — Annotations (e.g. `<'a>`) describing how long references are valid, so the borrow checker can verify them.
- **`unsafe`** — A block or function where the programmer opts out of some compiler guarantees (raw pointer dereference, calling foreign code). Safe abstractions are normally built on top of small `unsafe` cores.
- **MSRV** — Minimum Supported Rust Version: the oldest toolchain a crate guarantees to build with. Matters for libraries consumed by conservative downstream projects.
- **Edition** — Rust's opt-in mechanism for (rare) breaking language changes (2015, 2018, 2021, 2024). Crates declare their edition in `Cargo.toml`; editions interoperate.
- **Async / `.await`** — Rust's cooperative concurrency model. Futures are polled by an async runtime (e.g. Tokio); the language itself ships no runtime.
- **Runtime** — An async executor + reactor (Tokio, async-std, smol). Required to actually run `async` code.
- **`no_std`** — Crates usable without the standard library, for embedded/bare-metal targets. A key filter when evaluating embedded crates.
- **FFI** — Foreign Function Interface: calling C (or other languages) from Rust and vice versa, usually through `unsafe` bindings.
- **Procedural macro** — Code that generates code at compile time (derive macros like `Serialize`, attribute macros, function-like macros).
- **docs.rs** — Auto-generated documentation hosting for every published crate version.
- **rust-analyzer** — The official language server powering IDE support.
- **Clippy** — The official linter with hundreds of extra checks beyond `rustc`.
- **rustfmt** — The official code formatter.
- **Miri** — An interpreter for detecting undefined behavior in `unsafe` code; used in CI by careful projects.
- **WASM** — WebAssembly: Rust is a first-class language for compiling to WASM, for browsers and standalone runtimes (Wasmtime, Wasmer).
- **Soundness** — A safe API is *sound* if no combination of safe calls can trigger undefined behavior. A major evaluation criterion for `unsafe`-heavy crates.
