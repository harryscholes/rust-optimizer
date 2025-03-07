# CHANGELOG

## 0.12.0

- Reorganize project to use multi-stage builds instead of different docker files. This
  way no `cosmwasm/base-optimizer` image is expected on DockerHub.

## 0.11.5

- Bump Rust to 1.54.0

## 0.11.4

- Bump Rust to 1.53.0

## 0.11.3

- Remove `-n` from `echo` to flush logs early.
- Consolidate log style.
- Revert shell to `/bin/ash`.

## 0.11.2

- Fix target path for \*.wasm files.

## 0.11.1

- Issues when running `workspace-optimizer` in CircleCI (cosmwasm-plus #273).
  Revert to using `/bin/sh` for shell.

## 0.11.0

- Use precompiled sccache
- Reduce image size by deleting unnecessary files
- `cosmwasm/workspace-optimizer`: migrate from Rust nightly to stable (1.51.0)
- Migrate to alpine-based Rust images for smaller images

## 0.10.9

- `cosmwasm/rust-optimizer`: bump Rust to 1.51.0

## 0.10.8

- `cosmwasm/rust-optimizer`: bump Rust to 1.50.0
- `cosmwasm/workspace-optimizer`: bump Rust to nightly-2021-03-01

## 0.10.7

- Add shared build cache (sccache) to rust-optimizer

## 0.10.6

- Add support for building multiple non-workspace contracts at once (#25)

## 0.10.5

- Remove `trzeci/emscripten` dependency and install `wasm-opt` manually
- Upgrade `wasm-opt` to version 96

## 0.10.4

- `cosmwasm/rust-optimizer`: bump Rust to 1.47.0
- `cosmwasm/workspace-optimizer`: bump Rust to nightly-2020-10-14

## 0.10.3

- `cosmwasm/rust-optimizer`: bump Rust to 1.45.2

## 0.9.1

- Bump Rust to 1.45.2

## 0.10.2

- Split into `cosmwasm/rust-optimizer` and `cosmwasm/workspace-optimizer` to
  restore 0.9 stability for single contract builds while building adding support
  for monorepo builds. `cosmwasm/workspace-optimizer` now uses Rust
  `nightly-2020-08-20`.

## 0.10.1

- Rename `./artifacts/contracts.txt` to `./artifacts/checksums.txt`.

## 0.10.0

- Initial attempt to support workspace repos. Contracts are now writtien to
  `./articfacts/{contract name}.wasm` and `./artifacts/contracts.txt`.

## 0.9.0

- Bump Rust to 1.45.0

## 0.8.0

- Rename Github repo from `confio/cosmwasm-opt` to `CosmWasm/rust-optimizer`
- Rename Docker name from `confio/cosmwasm-opt` to `cosmwasm/rust-optimizer`
- Bump Rust to 1.43.1

## 0.7.3

- Avoid using CosmWasm shortcut `cargo wasm` since the config file
  `.cargo/config` is not included in creates.io source code publications.

## 0.7.2

**Note:** This version cannot be used for reproducible builds from crates.io
sources and should not be used. 0.7.0, 0.7.1 and 0.7.3 unaffected.

- Avoid using `web-pack` by doing the stripping directly. This removes the
  dependency in `wasm-bindgen` in contracts.
- Bump Rust to 1.41.1

## 0.7.1

- Avoid building schema during optimization. This belongs to the development
  flow, not to the reproducible build flow.

## 0.7.0

- Bump emscripten to 1.39.8-fastcomp
- Bump Rust to 1.41.0
