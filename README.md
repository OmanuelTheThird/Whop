# Whop CLI

## Getting started

### 1. Install

Pick whichever fits your machine:

- **macOS / Linux**

  ```sh
  curl -fsSL https://whop.com/install.sh | sh
  ```

- **Homebrew**

  ```sh
  brew install whopio/tap/whop
  ```

- **npm** (any platform, needs Node.js 22+)

  ```sh
  npm install -g @whop/cli
  ```

### 2. Confirm it installed

```sh
whop --version
```

### 3. Sign in

```sh
whop login
```

- `whop login --method oauth` opens a browser.
- For headless setups: `whop login --method api-key --apiKey whop_xxx`

### 4. Select the business the CLI should act on

```sh
whop quickstart
```

## Install script options

[`install.sh`](install.sh) reads these environment variables:

| Variable | Description |
| --- | --- |
| `WHOP_INSTALL_DIR` | Install location. Defaults to `$XDG_BIN_HOME`, then the `bin` directory next to `$XDG_DATA_HOME`, then `~/.local/bin`. |
| `WHOP_INSTALL_VERSION` | Version to install, e.g. `0.1.0`. Defaults to the latest release. |
| `WHOP_INSTALL_BASE_URL` | Override the directory assets are downloaded from (any URL `curl` accepts, including `file://`). Takes priority over `WHOP_INSTALL_VERSION`. |
| `WHOP_INSTALL_NO_MODIFY_PATH` | If set, never edit shell profiles; print the `PATH` line to add instead. |

For example, to install a specific version without touching your shell profile:

```sh
curl -fsSL https://whop.com/install.sh | WHOP_INSTALL_VERSION=0.1.0 WHOP_INSTALL_NO_MODIFY_PATH=1 sh
```

The script supports macOS and Linux on x64 and arm64, and verifies the download against the release's `SHA256SUMS` before installing. On other platforms, use npm.
