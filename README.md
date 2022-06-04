# Rust
My Rust Notes.

---
# Basic cli

## update
```
rustup update stable
```
## version
```
rustc --version
rustup --version
cargo --version
```
## compile a file
```
rustc main.rs
```
## initiate a project
```
cargo new <project-name>
cd <project-name>
```
## initiate a project in same folder
```
cargo init
```
## compile a project
```
cargo build
```
## compile and run a project
```
cargo run
```
## install a package
```
cargo install <package-name>
```
## install a package from a git repository
```
cargo install <package-name> --git <git-url>
```
## compile a project with specific target
```
cargo build --target x86_64-unknown-linux-gnu
```
## compile a project with specific target and specific profile
```
cargo build --target x86_64-unknown-linux-gnu --release
```
## compile a project with specific profile
```
cargo build --release
```
## compile a project with specific profile and specific features
```
cargo build --release --features "test"
```
## compile a project with specific features
```
cargo build --features "test"
```

---
# Code