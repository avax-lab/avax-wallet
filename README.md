# AVAX Wallet

**Quick, self‑custodial wallet for the Avalanche ecosystem**  
Store, swap and stake AVAX plus bridged BTC, ETH, USDC, USDT and any ARC‑20/ERC‑20 token on Avalanche C‑Chain.

![banner](public/og‑banner.png)

> **Prefer a native app?** Scroll to **[Desktop downloads](#desktop-downloads)** or use the web/PWA build at `wallet.avax.network`.

---

## Table of contents
- [Key features](#key-features)
- [Desktop downloads](#desktop-downloads)
- [Getting started](#getting-started)
- [Development workflow](#development-workflow)
- [Building for production](#building-for-production)
- [Running tests](#running-tests)
- [Security disclosure](#security-disclosure)
- [Contributing](#contributing)
- [License](#license)

---

## Key features
* **Cross‑platform:** Runs in any modern browser, as a PWA you can “install”, or as native Windows/macOS/Linux binaries.  
* **HD wallets & hardware support:** BIP‑39/BIP‑44 seed phrases, Ledger and Trezor connectivity.  
* **Subnet & token aware:** Automatic discovery of X / P / C chains, Subnets, NFTs and custom ARC‑20/ERC‑20 tokens.  
* **One‑click staking:** Delegate or validate AVAX with automatic reward tracking.  
* **Built‑in DEX & bridge:** Aggregated swaps and Core bridge for BTC ↔ AVAX.  
* **Open source & auditable:** TypeScript + Vue 2, powered by `@avalabs/avalanche-wallet-sdk`.  

---

## Desktop downloads
Pre‑built installers are published on the **[Releases](../../releases)** page for every tagged version.

| OS            | File name                              | Notes                             |
| ------------- | -------------------------------------- | --------------------------------- |
| **Windows**   | `avax-wallet‑Setup‑<version>.exe`      | 64‑bit installer, code‑signed     |
| **macOS**     | `avax-wallet‑<version>.dmg`            | Universal build (Apple & Intel)   |
| **Linux**     | `avax-wallet‑<version>.AppImage`       | Works on most distros             |

Each archive ships with `SHA256SUMS` and a detached PGP signature – **always verify before running**.

---

## Getting started

```bash
git clone https://github.com/avax-lab/avax-wallet.git
cd avax-wallet
yarn install        # or npm ci
yarn serve          # https://localhost:5000 with hot reload
```

Default network is **mainnet**. Switch to Fuji or a local node via **Settings → Network** or set `VUE_APP_NETWORK` before `yarn serve`.

### Prerequisites
- **Node ≥ 16**
- **Yarn classic** (or npm ≥ 7)
- Optional: a local [`avalanchego`](https://github.com/ava-labs/avalanchego) node for offline testing

---

## Development workflow

| Command          | Purpose                              |
| ---------------- | ------------------------------------ |
| `yarn serve`     | Dev server with hot reload (HTTPS)   |
| `yarn lint`      | ESLint + TypeScript checks           |
| `yarn test`      | Jest unit suite                      |
| `yarn cypress`   | Headless end‑to‑end tests            |
| `yarn format`    | Prettier auto‑format                 |

> **Firefox tip:** The dev server uses self‑signed HTTPS. Launch with `USE_HTTP=1 yarn serve` or import the certificate if Firefox blocks `localhost` SSL.

---

## Building for production

```bash
# Web/PWA build (static files in /dist)
yarn build

# Native desktop builds (Electron, requires platform‑specific signing)
yarn electron:build
```

Artifacts appear in `dist_electron/` and are uploaded automatically by CI when you push a tag like **v1.2.3**.

---

## Running tests

```bash
yarn test            # Jest unit tests
yarn cypress         # Headless e2e
yarn cypress:open    # Interactive e2e runner
```

---

## Security disclosure
Please **do not file GitHub issues for vulnerabilities**.  
Email `security@avax‑lab.dev` or use the public key in `SECURITY.md`. Responsible‑disclosure credits are added to the changelog.

---

## Contributing
1. Fork and create a feature branch.  
2. Run `yarn lint && yarn test` before opening a PR.  
3. Sign commits with the Developer Certificate of Origin (`git commit -s`).  

See **`CONTRIBUTING.md`** for detailed guidelines.

---

## License
BSD 3‑Clause – see [`LICENSE.md`](LICENSE.md) for the full text.
