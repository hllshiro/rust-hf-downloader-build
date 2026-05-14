# rust-hf-downloader Build

Auto-build portable binaries from [rust-hf-downloader](https://github.com/JohannesBertens/rust-hf-downloader) source code on crates.io.

## What is rust-hf-downloader?

A Terminal User Interface (TUI) application for searching, browsing, and downloading models from the HuggingFace model hub. Supports both interactive TUI mode and headless CLI mode.

**Features**: Interactive search, advanced filtering, GGUF quantization info, multi-threaded download, SHA256 verification, gated model support, resume, and more.

## Build Targets

| Platform | Architecture | Archive |
|----------|-------------|---------|
| Windows | x64 | `.zip` |
| Linux | x64 | `.tar.gz` |
| Linux | ARM64 | `.tar.gz` |
| macOS | x64 | `.tar.gz` |
| macOS | ARM64 | `.tar.gz` |

## Build Trigger

- **Automatic**: Every 6 hours, checks crates.io for new versions
- **Manual**: `workflow_dispatch` from GitHub Actions UI

## Usage

After building, download the appropriate binary for your platform from [Releases](https://github.com/hllshiro/rust-hf-downloader-build/releases).

```bash
# TUI mode (interactive)
rust-hf-downloader

# CLI mode (headless)
rust-hf-downloader --headless search "llama"
rust-hf-downloader --headless download "TheBloke/llama-2-7b-GGUF" --quantization "Q4_K_M"
rust-hf-downloader --headless resume
```

## Manual Build

Trigger from the [Actions](https://github.com/hllshiro/rust-hf-downloader-build/actions) tab:

1. Select **Manual Build**
2. Click **Run workflow**
3. Optionally specify a version (leave empty for latest)
4. Choose whether to publish as a Release
