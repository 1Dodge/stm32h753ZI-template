# STM32H753ZI plug and play template

#### This template includes all files and configs necessary to print "Hello, Rust" every second over terminal (probe-rs).

## Dependencies:

### 1. `flip-link`:

```bash
cargo install flip-link
```

### 2. `probe-rs`:

Install **probe-rs** by following the instructions at <https://probe.rs/docs/getting-started/installation/> or installing the vs-code extension.

### 3. [`cargo-generate`]:

```bash
cargo install cargo-generate
```

[`cargo-generate`]: https://crates.io/crates/cargo-generate

> *Note:* You can also just click on `Use this template` instead of using `cargo-generate`.

## Setup

### 1. Initialize the project template
#### Linux / Mac
```bash
cargo generate \
  --git https://github.com/1Dodge/stm32h753ZI-template \
  --branch main \
  --name my-app
```

#### Windows CMD
```bash
cargo generate ^
  --git https://github.com/1Dodge/stm32h753ZI-template ^
  --branch main ^
  --name my-app
```

#### Windows PowerShell
```bash
cargo generate `
  --git https://github.com/1Dodge/stm32h753ZI-template `
  --branch main `
  --name my-app
```

> *Note:* change `my-app` to your project name.

There now should be a new folder `my-app` with the template files in it.

### 2. Change config
#### 2.1 `cargo.toml`:
In `cargo.toml` you need to set the authors and the `name` to your project name.
```toml
authors = ["Your Name <optional@example.com>"]
name = "stm32h753ZI-template"
```

#### 2.2 `.vscode/launch.json`:
`my-app` needs to be changed to your project name. Otherwise vscode debugger wont run and fails.
```json
"programBinary": "${workspaceFolder}/target/thumbv7em-none-eabihf/debug/my-app",
```

### 3. Run the template

#### 3.1 Connect your STM32

#### 3.2 Everything is already configured so you just need to:
```bash
cargo run
```

The programm should flash and probe-rs debug output should be running. You should see `Hello, Rust` be printed every second.
