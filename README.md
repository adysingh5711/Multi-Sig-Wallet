# Weighted MultiSig Wallet with Governance Token

Welcome to the **Weighted MultiSig Wallet** project! This repository empowers builders to deploy a robust, flexible, and secure multi-signature wallet on Ethereum, enhanced with a custom governance token for weighted voting and execution. Built with [Foundry](https://book.getfoundry.sh/) and leveraging battle-tested [OpenZeppelin Contracts](https://github.com/OpenZeppelin/openzeppelin-contracts), this project is ready for rapid prototyping and production use.

## ✨ Project Overview

- **WeightedMultiSigWallet.sol**: A multi-signature wallet where each signer's voting power is determined by their balance of the custom `WalletGovToken`. Transactions require a configurable quorum (in token-weight) to execute, supporting advanced DAO and treasury use-cases.
- **WalletGovToken.sol**: An ERC20 governance token minted at wallet deployment. Token holders can transfer tokens (except to the wallet contract itself) and use them to participate in wallet governance and transaction approvals.

## 🛠️ Features

- **Weighted Signatures**: Transaction execution requires signatures whose combined token balances meet or exceed the quorum.
- **Dynamic Quorum**: The required quorum can be updated via wallet governance.
- **Executor Management**: Add or remove executors (signers) through on-chain proposals.
- **Secure ERC20**: Prevents sending tokens to the wallet contract or zero address.
- **Upgradeable Governance**: All critical parameters are modifiable via proposals.

## 🚀 Getting Started

### Prerequisites
- [Foundry](https://book.getfoundry.sh/getting-started/installation) (for Solidity development, testing, and deployment)
- Node.js (for some scripts, optional)

### Install Dependencies
Clone the repo and initialize submodules:
```sh
git clone <your-repo-url>
cd MultiSigWallet
git submodule update --init --recursive
```

### Build Contracts
```sh
forge build
```

### Run Tests
```sh
forge test
```

### Format Code
```sh
forge fmt
```

### Local Node (Optional)
```sh
anvil
```

## 🧩 Usage

- **Deploy the Wallet**: Deploy `WeightedMultiSigWallet` with your desired chain ID and quorum (per million). The deployer receives the initial supply of `WalletGovToken`.
- **Propose & Execute Transactions**: Collect signatures from token holders. When their combined weight meets the quorum, execute transactions via the wallet.
- **Manage Executors**: Add or remove executors through wallet proposals.

## 📂 Project Structure
- `src/WeightedMultiSigWallet.sol` — Main wallet contract
- `src/WalletGovToken.sol` — Custom governance token
- `lib/` — External dependencies (OpenZeppelin, Forge Std, etc.)
- `out/` and `cache/` — Build artifacts (gitignored)

## 📝 Configuration
- `foundry.toml` — Foundry project config
- `remappings.txt` — Library import remappings (e.g., OpenZeppelin)

## 🤝 Contributing
Builders are welcome! Fork, branch, and PR your improvements. For major changes, open an issue to discuss your ideas.

## 📖 Resources
- [Foundry Book](https://book.getfoundry.sh/)
- [OpenZeppelin Docs](https://docs.openzeppelin.com/contracts/)

---

*Build secure, composable, and community-driven smart contract wallets with confidence!*
