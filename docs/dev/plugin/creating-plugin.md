# 🧩 Building Guest Modules
The **Hydrust SDK** allows developers to create *high-performance*, *sandboxed* media scrapers using `Rust` and `WebAssembly`. 

Instead of writing brittle scripts, you are building **Guest Modules** that interface directly with the **Hydrust Host Engine**.

!!! info "Using `rust` is not the only option"
    You can use any programming language that compiles to WASM.
    There is a feature goal of providing several other SDK libraries in varius languages.

## 🏗️ The Host-Guest Relationship
In the **Hydrust** ecosystem, responsibilities are strictly decoupled:

- **The Host**: Manages the heavy lifting - network requests, GStreamer pipelines, and DRM decryption.
- **The Guest (You)**: Contains the "Intelligence" - parsing HTML/JSON, discovering manifests (HLS/DASH), and handling *site-specific* authentication logic.

Communication happens over the **WIT (WebAssembly Interface Type)** layer, ensuring that even if a plugin crashes, the Host Engine remains stable.

## 🛠️ Prerequisites
To build Hydrust plugins, you need the following tools installed on your development machine:

1. Rust Toolchain: [Install Rust](https://rustup.rs/)
2. Add WASM Target: 
    ```bash
    rustup target add wasm32-wasip1
    ```
3. Add Hydrust CLI (Optional but Recommended): Our tooling automates the scaffolding of new plugins.
    ```bash
    cargo install hydrust-cli
    ```
!!! warning "Hydrust CLI is not yet available"
    Hydrust CLI is still in active development and not yet available as a tool.
    The following guide assumes manual build process.


## 📂 Plugin Structure
A standard Hydrust plugin is a **specialized** Rust library. 
- Your `Cargo.toml` must specify `cdylib` to ensure it compiles to a standalone WASM module. 
- You also need our `hydrust-sdk` as a dependancy.


## 📜 The "Contract" (WIT)
Every plugin must implement the interfaces defined in our `provider.wit` file. This is the **"contract"** that tells the engine your plugin is compatible.


## 🚀 Quick Start

### Create a new project
```bash
cargo new --lib my-hydrust-plugin
cd my-hydrust-plugin
```

### Configure `Cargo.toml`
Set the crate type to `cdylib` and add the SDK: `cargo add hydrust-sdk`

```toml
[lib]
crate-type = ["cdylib"]

[dependencies]
hydrust-sdk = "0.1.2"
```

### Implement the Plugin
Edit `src/lib.rs` to handle events from the **Hydrust Core**:

```rust
use hydrust_sdk::{register_plugin, Handler};
use hydrust_sdk::events::Event;
use hydrust_sdk::metadata::PluginInfo;

#[derive(Default)]
struct MyPlugin;

impl Handler for MyPlugin {
    fn metadata(&self) -> PluginInfo {
        PluginInfo {
            name: "My Plugin".to_string(),
            version: "0.1.0".to_string(),
            author: "MyName".to_string(),
            description: "My plugin does wonders".to_string()
        }
    }

    fn on_event(&self, event: Event) {
        // Handle event logic here
    }
}

register_plugin!(MyPlugin);
```

### Compile your plugin
To compile your plugin run the following command:
```bash
cargo component build --release
```

This will produce a binary in your `./target/wasm32-wasip1/release` directory with an extension `.wasm`.

This is all you need to load it into **Hydrust**