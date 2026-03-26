# Vehicle Registration and Tracking DApp 🚗⛓️

A fully functional blockchain-based decentralized application for managing vehicle registration, tracking, and verification using Ethereum. This DApp ensures **transparency, immutability, and traceability** throughout the vehicle lifecycle.

## 🌟 Features

### ✅ Complete Implementation
- **Smart Contract Deployment** - Fully tested VehicleRegistry.sol contract
- **Role-Based Access Control** - Three distinct roles with specific permissions
- **Modern UI/UX** - Beautiful gradient designs with glassmorphism effects
- **Real-time Blockchain Interaction** - Direct Web3 integration with MetaMask
- **Comprehensive Testing** - Full test suite with 25+ test cases
- **Event Logging** - All actions logged on blockchain for audit trail

### 🎭 Three Primary Roles

#### 1️⃣ Dealership
- Register new vehicles on the blockchain
- Input vehicle details (VIN, color, model, company, owner info)
- View registration history
- Modern blue/indigo themed dashboard

#### 2️⃣ Service Centre
- Update vehicle mileage after service
- Record last service date automatically
- Search vehicles by VIN
- Validate mileage updates (prevents rollback)
- Modern green/emerald themed dashboard

#### 3️⃣ Company
- Verify vehicle authenticity
- Check complete service history
- View all vehicle details
- Validate vehicle registration status
- Modern purple/fuchsia themed dashboard

## 🛠️ Tech Stack

- **Frontend:** HTML5, Tailwind CSS 4, JavaScript (ES6+)
- **Backend:** Node.js, Express.js.
- **Blockchain:** Ethereum, Solidity ^0.8.19
- **Development Tools:** Truffle Suite, Ganache
- **Web3 Integration:** Web3.js v4
- **Authentication:** MetaMask wallet-based

## 📋 Prerequisites

Ensure you have these installed:
- **Node.js** (v14 or higher) - [Download](https://nodejs.org/)
- **npm** (comes with Node.js)
- **Ganache** - [Download](https://trufflesuite.com/ganache/)
- **MetaMask** browser extension - [Install](https://metamask.io/)

## 🚀 Quick Start

### 1. Installation

```bash
# Navigate to project directory
cd "Blockchain vehicle"

# Install all dependencies
npm install
```

### 2. Start Ganache

1. Open Ganache application
2. Create new workspace or use Quickstart
3. Configure: Host `127.0.0.1`, Port `7545`
4. Note the first 3 account addresses (for Dealership, Service Centre, Company)

### 3. Deploy Smart Contracts

```bash
# Compile contracts
npm run compile

# Deploy to Ganache
npm run migrate

# Run tests (optional but recommended)
npm test
```

### 4. Configure MetaMask

1. Install MetaMask extension
2. Add Ganache network:
   - Network Name: `Ganache Local`
   - RPC URL: `http://127.0.0.1:7545`
   - Chain ID: `1337`
   - Currency: `ETH`
3. Import the 3 Ganache accounts using private keys

### 5. Build CSS & Start Application

```bash
# Build Tailwind CSS
npm run build:css

# Start Express server
npm start
```

### 6. Access the Application

Open browser and go to: `http://localhost:3000`

**For detailed setup instructions, see [SETUP_GUIDE.md](./SETUP_GUIDE.md)**

## 📁 Project Structure

```
vehicle-blockchain-dapp/
├── contracts/
│   ├── VehicleRegistry.sol          # Main smart contract (169 lines)
│   └── Migrations.sol               # Truffle migrations
│
├── migrations/
│   ├── 1_initial_migration.js
│   └── 2_deploy_vehicle_registry.js # Contract deployment script
│
├── public/
│   ├── index.html                   # Login page with animated backgrounds
│   ├── dealership.html              # Vehicle registration dashboard
│   ├── servicecentre.html           # Service update dashboard
│   ├── company.html                 # Verification dashboard
│   └── styles/
│       └── output.css               # Compiled Tailwind CSS
│
├── src/
│   └── js/
│       ├── web3.js                  # Web3 provider setup
│       ├── auth.js                  # MetaMask authentication
│       ├── config.js                # Contract addresses & ABI
│       ├── dealership.js            # Registration logic
│       ├── servicecentre.js         # Mileage update logic
│       └── company.js               # Verification logic
│
├── server/
│   └── app.js                       # Express server
│
├── test/
│   └── vehicleRegistry.test.js      # Comprehensive test suite
│
├── truffle-config.js                # Truffle configuration
├── tailwind.config.js               # Tailwind CSS config
└── package.json                     # Dependencies & scripts
```

## 🎨 UI/UX Highlights

- ✨ **Animated blob backgrounds** on login page
- 🌈 **Role-specific gradient themes**
- 🪟 **Glassmorphism effects** with backdrop blur
- 🎯 **Custom icons** and smooth animations
- 📱 **Fully responsive** design
- 💫 **Real-time status updates** with toast notifications

## 🧪 Testing

Run the comprehensive test suite:

```bash
npm test
```

**Test Coverage:**
- Contract initialization ✅
- Vehicle registration (authorized & unauthorized) ✅
- Mileage updates (validation & access control) ✅
- Vehicle details retrieval ✅
- Verification system ✅
- Edge cases and error handling ✅

## 📝 Smart Contract Features

### VehicleRegistry.sol

**Key Functions:**
- `registerVehicle()` - Register new vehicle (Dealership only)
- `updateMileage()` - Update mileage and service date (Service Centre only)
- `getVehicleDetails()` - Retrieve vehicle information (Anyone)
- `verifyVehicle()` - Verify vehicle authenticity (Anyone)
- `isVehicleRegistered()` - Check registration status
- `getTotalVehicles()` - Get total registered vehicles
- `getAllVehicleVINs()` - Get all VINs

**Events:**
- `VehicleRegistered` - Emitted on new registration
- `MileageUpdated` - Emitted on mileage update
- `VehicleVerified` - Emitted on verification

**Security Features:**
- Role-based access control with modifiers
- Duplicate registration prevention
- Mileage rollback prevention
- Input validation on all functions
- Address validation in constructor

## 🔐 Security Considerations

- ✅ Role-based access control enforced at contract level
- ✅ MetaMask signature required for all transactions
- ✅ No centralized backend for critical operations
- ✅ All data immutably stored on blockchain
- ✅ Event logging for complete audit trail
- ✅ Input validation preventing empty/invalid data
- ✅ Reentrancy protection (no external calls in state-changing functions)

## 🌐 Deployment Options

### Local Development (Current Setup)
- **Network:** Ganache (127.0.0.1:7545)
- **Purpose:** Development and testing
- **Cost:** Free

### Ethereum Testnets
- **Sepolia** (Recommended) - Supports merge, active development
- **Goerli** - Being deprecated, use Sepolia instead
- **Mumbai** (Polygon testnet) - For lower gas costs
- **Purpose:** Pre-production testing with real network conditions
- **Cost:** Free testnet ETH from faucets

### Production Deployment
- **Ethereum Mainnet** - Most secure, highest gas costs
- **Polygon Mainnet** - Lower gas fees, faster transactions
- **Optimism/Arbitrum** - Layer 2 solutions for reduced costs
- **Purpose:** Real-world deployment
- **Cost:** Real ETH/MATIC required

**See deployment guide below for detailed instructions.**

## 🚢 How to Deploy

### Deploy to Sepolia Testnet

1. **Get Sepolia ETH:**
   - Visit Sepolia faucet (e.g., https://sepoliafaucet.com/)
   - Request testnet ETH for your accounts

2. **Update truffle-config.js:**
   ```javascript
   const HDWalletProvider = require('@truffle/hdwallet-provider');
   const mnemonic = "your twelve word mnemonic here";
   
   networks: {
     sepolia: {
       provider: () => new HDWalletProvider(mnemonic, 
         `https://sepolia.infura.io/v3/YOUR-INFURA-KEY`),
       network_id: 11155111,
       gas: 5500000,
       confirmations: 2,
       timeoutBlocks: 200,
       skipDryRun: true
     }
   }
   ```

3. **Deploy:**
   ```bash
   npm install @truffle/hdwallet-provider
   npx truffle migrate --network sepolia
   ```

4. **Update frontend config:**
   - Update `src/js/config.js` with new contract addresses
   - Change MetaMask network to Sepolia

### Deploy Frontend

**Option 1: Vercel (Recommended)**
```bash
npm install -g vercel
vercel deploy
```

**Option 2: Netlify**
```bash
npm install -g netlify-cli
netlify deploy
```

**Option 3: GitHub Pages**
```bash
# Build static files
npm run build:css

# Push to gh-pages branch
git subtree push --prefix public origin gh-pages
```

**Option 4: Traditional Hosting**
- Upload `public/`, `src/`, and `server/` folders
- Configure Node.js hosting
- Set environment variables
- Start with `npm start`

## 📊 NPM Scripts

```bash
npm start              # Start Express server
npm test              # Run Truffle tests
npm run compile       # Compile smart contracts
npm run migrate       # Deploy contracts to Ganache
npm run migrate:reset # Redeploy contracts (fresh)
npm run build:css     # Build production CSS
npm run watch:css     # Watch CSS changes (development)
```

## 🐛 Troubleshooting

**MetaMask Connection Issues:**
- Ensure Ganache is running on port 7545
- Check network settings in MetaMask (Chain ID: 1337)
- Try disconnecting and reconnecting
- Clear browser cache

**Transaction Failures:**
- Verify you're using correct account for the role
- Ensure account has sufficient ETH for gas
- Check contract is deployed (`npm run migrate`)
- Review transaction details in MetaMask

**Contract Not Found:**
- Run `npm run migrate:reset` to redeploy
- Check `src/js/config.js` has correct addresses
- Verify Ganache is running

**UI Issues:**
- Run `npm run build:css` to compile styles
- Hard refresh browser (Ctrl+Shift+R)
- Check browser console for errors

## 🤝 Contributing

This is an educational project demonstrating blockchain-based vehicle management. Feel free to fork and enhance!

## 📄 License

ISC

## 👨‍💻 Author

Built as a comprehensive blockchain development project showcasing:
- Smart contract development with Solidity
- Web3 integration with modern JavaScript
- Role-based decentralized applications
- Full-stack blockchain development
- Modern UI/UX with Tailwind CSS


