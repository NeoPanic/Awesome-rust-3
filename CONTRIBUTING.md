# Contributing to Awesome-rust

Thanks for helping keep this list accurate. This repo has strict honesty rules — please read them before opening a PR.

## What belongs here

- **The Rust ecosystem**: web frameworks, async runtimes, networking, databases & ORMs, serialization, CLI/TUI, GUI, game engines, WebAssembly, embedded/`no_std`, testing & observability, cryptography, and Cargo/build tooling.
- The Rust language itself, books, and tutorials are **out of scope** (see the exclusions table in the README for where to find those).

## Entry requirements (all must hold)

1. **Real and verifiable.** The crate/project must exist at the linked URL. `verified` is `true` only if you confirmed the entry on an official source (the project's repo, LICENSE file, or crates.io page) — never from a blog roundup alone.
2. **Honest license.** Copy the SPDX identifier from the project's actual LICENSE file or `Cargo.toml`. If the license can't be confirmed, set `"license": null`, `"verified": false`, and explain in `"unverified_reason"`.
3. **No invented facts.** No guessed star counts or descriptions. If you can't verify it, leave it `null` and say why.
4. **One category each.** Pick the single best-fitting `category`.

## How to add an entry

1. Add the entry to `data/rust.json` (keep the file's existing ordering: grouped by category):
   ```json
   {
     "name": "example-crate",
     "description": "One-line description, no hype.",
     "license": "MIT OR Apache-2.0",
     "category": "cli-tui",
     "repo": "https://github.com/org/example-crate",
     "homepage": "https://crates.io/crates/example-crate",
     "official_site": null,
     "stars": 1234,
     "verified": true,
     "unverified_reason": null
   }
   ```
   Use `null` (not `""`) for unknown `repo`/`official_site`/`stars`/`unverified_reason`.
2. Add the matching bullet to the right section in `README.md`: `- [example-crate](https://crates.io/crates/example-crate) — one-line description.`
3. Run the CI validation locally if you can (`python` 3.12+, see `.github/workflows/ci.yml`): it checks JSON validity, duplicate names/URLs, the README↔JSON cross-check, section counts, and TOC anchors.
4. Open a PR describing what you verified and where (link the official source).

## Link hygiene

- Prefer `https://` URLs; no URL shorteners.
- For crates, link the crates.io page as `homepage` unless the project has a real standalone site.
- If a project renamed/moved, update to the canonical URL and note it in `docs/status-changes.md`.

## What gets rejected

- Entries with invented licenses, stars, or descriptions.
- Dead links, or projects you can't confirm exist.
