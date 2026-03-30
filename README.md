[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](./LICENSE)
[![React](https://img.shields.io/badge/react-17-61dafb.svg)](https://react.dev/)
[![TypeScript](https://img.shields.io/badge/typescript-4.1-3178c6.svg)](https://www.typescriptlang.org/)
[![Solana](https://img.shields.io/badge/solana-wallet-14f195.svg)](https://solana.com/)

# sollet

Minimal Solana wallet for local development and self-hosted use.

## Features

| Area | Details |
| --- | --- |
| Keys | Create, import, export, and manage wallet keys |
| Signing | Sign transactions and connected app requests |
| RPC | Connect to Solana RPC endpoints and custom clusters |
| Tokens | View balances and work with SPL token accounts |

## Install

```bash
npm install
```

## Quick Usage

```bash
npm start
```

Open the local app in your browser and connect it to the Solana cluster you want to use.

## Configuration

| Variable | Default | Notes |
| --- | --- | --- |
| `HTTPS` | `true` | Enabled in `.env.development` |
| `SSL_CRT_FILE` | `./.cert/cert.pem` | Local dev certificate |
| `SSL_KEY_FILE` | `./.cert/key.pem` | Local dev key |

## Notes

- Built with React and TypeScript.
- Main source is in `src/`.
- Browser extension assets are in `extension/`.
