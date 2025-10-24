---
title: Rust Best Practices
inclusion: fileMatch
fileMatchPattern: '*.rs'
---

# Rust Best Practices

## Code Style
- Follow official Rust formatting with `rustfmt`
- Use meaningful variable and function names
- Use snake_case for variables, functions, and modules
- Use PascalCase for types, traits, and enum variants
- Use SCREAMING_SNAKE_CASE for constants and statics
- Limit line length to 100 characters (rustfmt default)

## Type Safety
- Leverage Rust's ownership system and borrow checker
- Use `Option<T>` instead of null values
- Use `Result<T, E>` for error handling
- Prefer owned types over borrowed when ownership is clear
- Use lifetimes explicitly when needed
- Implement appropriate traits (`Debug`, `Clone`, `PartialEq`)

## Error Handling
- Use `Result<T, E>` for recoverable errors
- Use `panic!` only for unrecoverable errors
- Use `?` operator for error propagation
- Create custom error types with `thiserror` crate
- Use `anyhow` for application-level error handling
- Handle errors at appropriate levels

## Code Organization
- Use Cargo for dependency management (`Cargo.toml`)
- Organize code into modules with `mod.rs` or single files
- Use `pub` keyword judiciously for public APIs
- Follow semantic versioning for crates
- Use workspaces for multi-crate projects
- Keep `main.rs` or `lib.rs` minimal

## Testing
- Write unit tests using built-in `#[test]` attribute
- Use integration tests in `tests/` directory
- Use `assert!`, `assert_eq!`, and `assert_ne!` macros
- Mock with traits and dependency injection
- Use `#[should_panic]` for panic testing
- Run tests with minimal output: `cargo test --quiet`
- Filter specific tests: `cargo test test_name`

## Performance
- Use iterators over manual loops when possible
- Prefer `Vec<T>` over `LinkedList<T>` for most use cases
- Use `Cow<T>` for clone-on-write scenarios
- Profile with `cargo flamegraph` or `perf`
- Use `#[inline]` sparingly and only when measured
- Leverage zero-cost abstractions and compile-time optimizations
