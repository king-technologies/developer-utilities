# Rust

### What is Rust?

- Rust is a systems programming language that runs blazingly fast, prevents segfaults, and guarantees thread safety.
- Rust is a multi-paradigm programming language focused on performance and safety, especially safe concurrency.
- Rust is syntactically similar to C++, but is designed to provide better memory safety while maintaining high performance.
- Rust is a systems programming language that combines strong compile-time correctness guarantees with fast performance.

### Installation

- [Rustup](https://rustup.rs/) is an installer for the systems programming language Rust.
- It is an official Rust project.
- Rustup installs rustc, cargo, rustup and other standard tools to Cargo's bin directory.
- Rustup is configured to use the official Rust distribution servers, which offer the latest official releases of Rust.
- Rustup manages these builds in a consistent way on every platform that Rust supports, enabling installation of Rust from the beta and nightly release channels as well as support for additional cross-compilation targets.
- Rustup is available for the GNU/Linux, macOS, and Windows platforms.
- Rustup also supports other platforms like the *BSDs, Solaris, and Android, but these are not officially supported.
- Rustup installs Rust from the official release channels, enabling you to easily switch between stable, beta, and nightly compilers and keep them updated.
- It also supports per-directory overrides based on the presence of a rust-toolchain file.

### Hello World

- The traditional first program for a new language is to print "Hello, world!" to the screen.
- In Rust, this can be done with the following code:

```rust
fn main() {
    println!("Hello, world!");
}
```

- This code uses the println! macro to print a string to the screen.
- Rust style is to indent with four spaces, not a tab.
- Rust code uses snake case as the conventional style for function and variable names.

## Cargo Watch

- First you have to install cargo-watch by running the following command:

```bash
cargo install cargo-watch
```

- Then you can use cargo-watch to automatically recompile your code when it changes:

```bash
cargo watch -x run
# or
cargo watch -q -c -x run # quiet, clear, execute, run
# or
cargo watch -q -c -x "run -q" # quiet, clear, execute, run quietly
# or
cargo watch -x 'run --release' # run in release mode
# or build in release mode with file watching
cargo watch -x 'build --release'

```

- This will run the `cargo run` command every time a file in your project changes.
- You can also use `cargo watch -x test` to run the tests every time a file changes.