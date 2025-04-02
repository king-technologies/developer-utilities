# New Project

To create a new project, run the following command:

```bash
cargo new project_name
# It will create a new directory with the project_name
```

or 

```bash
cargo new --bin project_name
# It will create a new directory with the project_name and a binary project
```

or 

```bash
cargo init
# It will create a new directory with a binary project
```

or 

```bash
cargo init --bin
# It will create a new directory with a binary project
```

# Switch Between Rust Versions

To switch between Rust versions, run the following command:

```bash
rustup default nightly
# It will switch to the nightly version of Rust
```

or 

```bash
rustup default stable
# It will switch to the stable version of Rust
```

# Cargo Watch

First you have to install cargo-watch by running the following command:

```bash
cargo install cargo-watch
```

Then you can use cargo-watch to automatically recompile your code when it changes:

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