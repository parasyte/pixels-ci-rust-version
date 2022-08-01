# `pixels-ci-version`

This exists as a separate repository from the main [`pixels`](https://crates.io/crates/pixels) crate for its MSRV testing. The produced binary does not do anything. In fact, it crashes because the mock window is not fully implemented. It is not intended to be used for anything other than building in CI.

It is necessary to use a separate repository to avoid the shared workspace. This example compiles the latest development branch of `pixels` on the oldest version of Rust possible. See [`Cargo.toml`](https://github.com/parasyte/pixels/blob/main/Cargo.toml) for the `rust-version` that will be used.

The `pixels` CI runs periodically. Because this repo does not include `Cargo.lock`, these periodic builds will always test the most recent list of dependencies.
