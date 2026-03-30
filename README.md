[![License](https://img.shields.io/badge/license-Apache--2.0-black.svg)](LICENSE)
[![Solana](https://img.shields.io/badge/network-Solana-14F195.svg)](https://solana.com/)
[![Yarn](https://img.shields.io/badge/package_manager-Yarn-2C8EBB.svg)](https://yarnpkg.com/)

# Sollet Wallet

Sollet is a full-featured desktop wallet for Solana. The repository includes the main application, key management and signing flows, SOL and SPL asset handling, custom RPC support, and related wallet integrations.

| Area | Included in this repository |
| --- | --- |
| Wallet core | account creation, import, export, mnemonic handling, signing flows |
| Assets | SOL balances, SPL tokens, token account operations |
| Connectivity | Solana RPC interaction, custom clusters, connection management |
| Integrations | Ledger support, swap flows, Solana Name Service, wallet connection flows |

## Project Layout

```text
src/
  components/    UI and wallet actions
  pages/         login, wallet, popup, connection views
  utils/         clusters, transactions, wallet logic, tokens, swap, name service
extension/src/   extension manifest, background script, content script, injected script
public/          base web assets
.cert/           local HTTPS certificates for development
```

## Requirements

- Node.js 14+ or 16
- Yarn 1.x
- a Unix-like shell for shell-based build steps

The project uses `react-scripts` and Yarn commands defined in `package.json`.

## Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/maxcore23/sollet.git
cd sollet
yarn
```

### Development HTTPS setup

Local development is configured to run over HTTPS.  
`.env.development` points `react-scripts` to certificate files stored in `.cert/`:

```env
HTTPS=true
SSL_CRT_FILE=./.cert/cert.pem
SSL_KEY_FILE=./.cert/key.pem
```

Before starting the app, make sure these files exist:

```text
.cert/cert.pem
.cert/key.pem
```

If the certificate pair is missing, `yarn start` will fail or run with an invalid local HTTPS setup.

To prepare the directory:

```bash
mkdir -p .cert
# place your local certificate and key here
# expected names:
# .cert/cert.pem
# .cert/key.pem
```

If HTTPS is not required for your local workflow, adjust `.env.development` accordingly. Do that only if your target flow does not depend on secure-context browser APIs.

## Running the app

Start the wallet in development mode:

```bash
yarn start
```

The app entry is `src/index.js`, the main shell is wired through `src/App.js`, and the main wallet screens live under `src/pages`.

## Development commands

```bash
yarn start            # run local development server
yarn build            # build the main app
yarn build:extension  # build the extension package
yarn test             # run tests
```

## Notes

- Local development expects certificates in `.cert/`.
- The project uses Yarn scripts as the primary workflow.
- Some build steps rely on a Unix-like shell environment.

## License

Apache-2.0
