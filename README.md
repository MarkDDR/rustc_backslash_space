# What is this?
When you run either `cargo check` or `cargo build`, rustc will eat your memory rapidly until you run out (only tested up to about 32GB)

# How?
In `Cargo.toml`, add the following dependency
```toml
tokio = { version = "1.2.0", features = ["macros"] }
```

in `src/main.rs`, have the following
```rust
#[tokio::main]
async fn main() {
    let _backslash_space = "\ ";
}
```
