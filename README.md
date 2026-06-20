# solana_token

[![Solana](https://img.shields.io/badge/Solana-v2.0-000000?style=for-the-badge&logo=solana)](https://solana.com)
[![Rust](https://img.shields.io/badge/Rust-2025-CE412B?style=for-the-badge&logo=rust)](https://www.rust-lang.org)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## Overview

**Tiziran Token (TIZ)** — SPL token implementation on the Solana blockchain.

This repository contains the token metadata, logo assets, and configuration for the TIZ token deployed on Solana mainnet.

## What is an SPL Token?

SPL (Solana Program Library) tokens are the fungible token standard on Solana, analogous to ERC-20 on Ethereum. Key features:

- **~400ms finality** with ~65,000 TPS throughput
- **Low transaction fees** (~0.000005 SOL)
- **Program Derived Addresses (PDAs)** for deterministic account ownership
- **Token-2022 extensions**: transfer fees, confidential transfers, non-transferable tokens, CPI guards

## 2025-2026 Solana Ecosystem Updates

### Token-2022 (Token Extensions)
The Solana ecosystem has fully adopted Token Extensions as the standard for new token deployments:

- **Transfer Fees**: Automatic on-chain fee collection per transfer
- **Confidential Transfers**: ZK-proofs for private balances
- **Permanent Delegate**: Granting a delegate ongoing transfer authority
- **Non-Transferable Tokens**: Soulbound tokens for identity/credentials
- **Memo Required**: Enforce memo on every transfer for compliance
- **Default Account State**: Tokens minted as frozen by default (KYC/AML)

### Tooling (2025-2026)

| Tool | Version | Purpose |
|------|---------|---------|
| Solana CLI | v2.1+ | Key management, deployment, RPC |
| Anchor Framework | v0.31+ | Rust-based smart contract framework |
| SPL Token CLI | v2.1+ | Token mint/transfer/freeze operations |
| Jito SDK | v2.0+ | MEV-optimized transaction bundles |
| Helius SDK | v1.3+ | Webhook indexing, enhanced RPC |
| Steel | v0.9+ | Low-level Solana program framework |
| Mollusk | v0.12+ | Solana program testing |

### On-chain Data (2025-2026)
- **Solana Firedancer** (Jump Crypto): Achieved 1M+ TPS in testnet (2025)
- **State Compression**: Merkle tree-based NFTs and on-chain state reducing costs by 5000x+
- **Solana Actions & Blinks**: On-chain actions convertible to shareable links (URLs)
- **Solana Mobile dApp Store**: Saga 2 phone with native Solana integration

## Project Structure

```
solana_token/
├── README.md
├── LICENSE          # MIT License
├── tiziran.png     # Token logo (high-res)
└── tiziran.jpeg    # Token logo (compressed)
```

## Token Details

| Property | Value |
|----------|-------|
| Name | Tiziran |
| Symbol | TIZ |
| Blockchain | Solana |
| Standard | SPL Token / Token-2022 |
| Logo | `tiziran.png` |

## Getting Started

### Prerequisites

```bash
# Install Solana CLI
sh -c "$(curl -sSfL https://release.anza.xyz/stable/install)"

# Verify installation
solana --version

# Install Anchor CLI
cargo install --git https://github.com/coral-xyz/anchor avm --force
avm install latest
avm use latest

# Install SPL Token CLI
cargo install spl-token-cli
```

### Creating a Token

```bash
# Create a new SPL token
spl-token create-token

# Create a token account
spl-token create-account <TOKEN_ADDRESS>

# Mint tokens
spl-token mint <TOKEN_ADDRESS> 1000000
```

### Deploying Token-2022

```bash
# Initialize with extensions
spl-token create-token --program-id TokenzQdBNbLqP5VEhdkAS6EPFLC1PHnBqCXEpPxuEb \
  --enable-transfer-fee --transfer-basis-points 50 --transfer-maximum-fee 5000
```

## Resources

- [Solana Documentation](https://docs.solanalabs.com)
- [SPL Token Program](https://spl.solana.com/token)
- [Token Extensions Guide](https://spl.solana.com/token-2022)
- [Anchor Book](https://www.anchor-lang.com)
- [Solana Cookbook](https://solanacookbook.com)

## License

MIT License - see [LICENSE](LICENSE) for details.

---

**Maintainer:** [Farshid Pirahansiah](https://github.com/pirahansiah)
