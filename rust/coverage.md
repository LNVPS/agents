# Test Coverage Requirements — Rust

See [../coverage.md](../coverage.md) for the base rules.

## Rust-Specific Instructions

### Generate the coverage report

Using `cargo-llvm-cov`:

```bash
cargo llvm-cov --summary-only
```

For a line-level breakdown, open the HTML report:

```bash
cargo llvm-cov --open
```

If your tests require single-threaded execution:

```bash
cargo llvm-cov --summary-only -- --test-threads=1
```

### Alternative: cargo-tarpaulin

```bash
cargo tarpaulin --out Html --output-dir coverage/
```

### Interpreting the report

- The terminal summary shows per-file `Fns %`. A file you touched must reach **100%** for functions you added.
- The HTML report highlights uncovered lines in red.
- Functions that are `#[cfg(test)]`-only or compile-time-only (e.g., `derive` impls) are excluded automatically.
- `#[cfg(not(tarpaulin_include))]` or `#[coverage(off)]` can exclude code that genuinely cannot be tested.

### Checklist additions

- [ ] `cargo llvm-cov --summary-only` shows 100% function coverage for every file you modified
- [ ] `cargo test` passes with no failures
- [ ] `cargo clippy --all-features` produces no warnings
