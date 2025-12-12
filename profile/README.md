# HSLU Module Review DApp

A decentralized platform (DApp) for students of Hochschule Luzern (HSLU) to transparently and tamper-proof record module ratings and reviews. Built with Solidity smart contracts and Truffle.

## Features

- **Decentralized Storage**: Module reviews stored on-chain
- **Student Verification**: Soul-Bound Token (SBT) badges for verified HSLU students
- **Community-Driven**: Students can add modules and write reviews
- **Transparent Ratings**: Ratings, workload, and difficulty assessments

## Prerequisites

- **Node.js** (v18 or higher)
- **npm** (comes with Node.js)
- **MetaMask** browser extension
- **Git**

## Quick Start

### 1. Clone the Repositories 
```bash
git clone https://github.com/BCHAIN-MN/HSLU-Module-Review-DApp.git
cd HSLU-Module-Review-DApp
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Start Ganache (Local Blockchain)

In a terminal, start Ganache:
```bash
npx ganache --port 8545 --chain.chainId 1337 --wallet.totalAccounts 10
```

**Attention** - Ganache must be running for the application to work.

### 4. Deploy Smart Contracts

In a **new terminal**:
```bash
cd HSLU-Module-Review-DApp
npm run migrate:resetThis will deploy:
- `StudentIdentity` contract (Soul-Bound Token for student verification)
- `ModuleReviews` contract (Module and review management)
```

**Important**: Note the contract addresses from the output. You'll need them for the frontend configuration.

### 5. Seed Test Data

npm run seedThis populates the contracts with:
- 15 HSLU module IDs
- Verification badges for 3 test students
- Sample reviews for 6 modules

### 6. Configure MetaMask

1. Open MetaMask extension
2. Click the network dropdown → "Add Network" → "Add a network manually"
3. Enter the following:
   - **Network Name**: Ganache Local
   - **RPC URL**: `http://127.0.0.1:8545`
   - **Chain ID**: `1337`
   - **Currency Symbol**: ETH
4. Click "Save"

### 7. Import Test Account

1. In MetaMask, click the account icon → "Import Account"
2. Use one of the private keys from the terminal Output when you initialized Ganache!
3. The first account (index 0) is the contract owner and acts admin account for student verification

### 8. Web UI setup 

**Clone the Repo**
```bash
git clone https://github.com/BCHAIN-MN/interface
cd inerface
```

```bash
npm installCreate `.env.local`:

NEXT_PUBLIC_MODULE_REVIEWS_ADDRESS=<ModuleReviews-address-from-step-4>
NEXT_PUBLIC_STUDENT_IDENTITY_ADDRESS=<StudentIdentity-address-from-step-4>
```

**Start the frontend:**
```bash
npm run devOpen http://localhost:3000 in your browser.
```

## Available Scripts

- `npm run compile` - Compile smart contracts
- `npm run migrate` - Deploy contracts (without reset)
- `npm run migrate:reset` - Reset and redeploy all contracts
- `npm run test` - Run Truffle tests
- `npm run seed` - Populate contracts with test data
