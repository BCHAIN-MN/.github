# HSLU Module Review DApp

A decentralized platform (DApp) for students of Hochschule Luzern (HSLU) to transparently and tamper-proof record module ratings and reviews.

## Live Deployment

- **Frontend**: [Link](https://interface-khaki-iota.vercel.app/)
- **Network**: Polygon Amoy Testnet
- **Block Explorer**: [Polygonscan Amoy](https://amoy.polygonscan.com/)

## Features

* **Decentralized Storage**: Module reviews stored on-chain on Polygon Amoy testnet
* **Student Verification**: Soul-Bound Token (SBT) badges for verified HSLU students
* **Community-Driven**: Students can add modules and write reviews (Governance function comming soon...)
* **Transparent Ratings**: Ratings, workload, and difficulty assessments
* **Admin Panel**: At the moment, contract owner can issue verification badges to students

## Smart Contracts (Deployed on Polygon Amoy)

- **StudentIdentity**: 0x12988870ec1adb756e57970279ac3475715368
  - Soul-Bound Token (SBT) for student verification
  - Non-transferable NFT badges
  

- **ModuleReviews**: 0x1ba60a98e0ae46cd47dc85c440057f6ef9f5e2e1
  - Module management and review storage
  - On-chain review data

View contracts on [Polygonscan Amoy](https://amoy.polygonscan.com/):
- StudentIdentity: [Link](https://amoy.polygonscan.com/address/0x12988870ec1adb756e57970279ac3475715368df#events)
- ModuleReviews: [Link](https://amoy.polygonscan.com/address/0x1ba60a98e0ae46cd47dc85c440057f6ef9f5e2e1#events)

## Prerequisites

* **Node.js** (v18 or higher)
* **npm** (comes with Node.js)
* **MetaMask** browser extension
* **Git**
* **Polygon Amoy Testnet MATIC** (get from [Polygon Faucet](https://faucet.polygon.technology/) or [Stake Pool](https://faucet.stakepool.dev.br/amoy)) 

## Quick Start (Local Setup of the Frontend)

### 1. Clone the Repositories

```bash
# Frontend Repository
cd ..
git clone https://github.com/BCHAIN-MN/interface.git
cd interface
```

### 2. Install Dependencies

**Frontend:**
```bash
cd ../interface
npm install
```

### 3. Configure Frontend

Create `.env.local` in the `interface` directory:

```env
NEXT_PUBLIC_MODULE_REVIEWS_ADDRESS=0x1ba60a98e0ae46cd47dc85c440057f6ef9f5e2e1
NEXT_PUBLIC_STUDENT_IDENTITY_ADDRESS=0x12988870ec1adb756e57970279ac3475715368df
```

### 4. Configure MetaMask for Polygon Amoy

1. Open MetaMask extension
2. Click the network dropdown → "Add Network" → "Add a network manually"
3. Enter the following:
   - **Network Name**: Polygon Amoy
   - **RPC URL**: `https://rpc-amoy.polygon.technology`
   - **Chain ID**: `80002`
   - **Currency Symbol**: MATIC
   - **Block Explorer URL**: `https://amoy.polygonscan.com`
4. Click "Save"

### 5. Get Testnet MATIC

1. Visit [Polygon Faucet](https://faucet.polygon.technology/)
2. Select "Polygon Amoy" network
3. Enter your wallet address
4. Request testnet MATIC (you'll need this for gas fees)

### 6. Start the Frontend

```bash
cd interface
npm run dev
```

Open http://localhost:3000 in your browser.


## Project Structure

```
HSLU-Module-Review-DApp/
├── src/
│   ├── contracts/          # Solidity smart contracts
│   │   ├── StudentIdentity.sol
│   │   └── ModuleReviews.sol
│   └── abis/               # Compiled contract ABIs
├── migrations/            # Truffle migration scripts
├── test/                  # Contract tests
└── scripts/               # Utility scripts

interface/
├── app/                   # Next.js app directory
│   ├── page.tsx           # Main page
│   └── admin/             # Admin panel
├── components/            # React components
├── lib/                   # Contract interaction logic
└── public/                # Static assets
```

## Usage

### For Students

1. Connect your MetaMask wallet (Polygon Amoy network)
2. Request verification by contacting the contract owner
3. Once verified, you can:
   - Browse modules
   - Write reviews for modules
   - View other students' reviews

### For Admins

1. Connect with the contract owner account
2. Access the Admin Panel at `/admin`
3. Issue verification badges to students
4. View all verified students

## Technology Stack

* **Smart Contracts**: Solidity 0.8.20
* **Development Framework**: Truffle
* **Local Testing**: Ganache
* **Frontend**: Next.js 16, React 18, TypeScript
* **Testnet Blockchain**: Polygon Amoy Testnet
* **Web3 Library**: ethers.js
* **UI Components**: shadcn/ui, Radix UI

## Contributing

This is a project for HSLU students. For contributions, please contact the repository maintainers.

## Links

* **Organization**: [BCHAIN-MN](https://github.com/BCHAIN-MN)
* **Smart Contracts Repo**: [HSLU-Module-Review-DApp](https://github.com/BCHAIN-MN/HSLU-Module-Review-DApp)
* **Frontend Repo**: [interface](https://github.com/BCHAIN-MN/interface)
* **Polygon Amoy Explorer**: [Polygonscan Amoy](https://amoy.polygonscan.com/)
* **Polygon Faucet**: [Get Testnet MATIC](https://faucet.polygon.technology/)

