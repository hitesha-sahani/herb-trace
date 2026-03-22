

---

# 🌿 HerbTrace

### Blockchain-Powered Herb Supply Chain Tracking

**HerbTrace** is a full-stack Web3 application designed to track medicinal herbs across their entire lifecycle —
from **farmer → processor → lab → consumer** — ensuring **transparency, traceability, and tamper-proof records**.

---

## 🔍 Overview

HerbTrace combines blockchain, decentralized storage, and a modern web stack to create a trustless system for herbal supply chains.

### 🧱 Tech Stack

* ⚙️ **Backend:** Node.js + Express
* 🎨 **Frontend:** HTML, CSS, JavaScript
* ⛓ **Blockchain:** Ethereum (EVM-compatible)
* 📦 **Storage:** IPFS via Pinata
* 🔐 **Auth:** JWT
* 🗄 **Database:** Local JSON (off-chain history)

---

## 🔗 Blockchain Compatibility

HerbTrace is fully compatible with **any EVM network**.

### 🧪 Local Networks

* Ganache
* Hardhat
* Anvil (Foundry)
* Geth Private Chain

### 🌐 Public Testnets

* Sepolia
* Goerli
* Holesky
* Polygon Amoy
* BNB Smart Chain Testnet

### ⚙️ Configuration

Update your `.env`:

```env
RPC_URL=http://127.0.0.1:8545
GANACHE_PK=0xyourPrivateKey
```

Backend automatically connects:

```js
const provider = new ethers.providers.JsonRpcProvider(process.env.RPC_URL);
const signer = new ethers.Wallet(process.env.GANACHE_PK, provider);
```

✅ No code changes required when switching networks.

---

## 🚀 Features

### 👨‍🌾 Farmer Module

* Add herb batches
* Auto-generate Batch IDs
* Upload images (IPFS)
* Capture geo-location
* Store on blockchain + local DB

---

### 🏭 Processor Module

* View incoming batches
* Add processing details
* Record facility information
* Log events on blockchain

---

### 🔬 Lab Module

* Upload test reports (PDF)
* Store reports on IPFS
* Attach quality results
* Add geo-coordinates
* Blockchain verification

---

### 🧾 Consumer View

* Scan QR code
* View full batch history
* Timeline visualization
* Interactive geo-map tracking

---

## 🗂 Project Structure

```
herb-trace/
│
├── backend/
│   ├── server.js
│   ├── contracts/
│   ├── scripts/
│   ├── routes/geo.js
│   ├── localDB.json
│   ├── pinataHelper.js
│
├── frontend/
│   ├── index.html
│   ├── login.html
│   ├── farmer.html
│   ├── processor.html
│   ├── lab.html
│   ├── consumer.html
│   ├── qr.html
│   ├── style.css
│
└── README.md
```

---

## ⚙️ Installation & Setup

### 1️⃣ Install Dependencies

```bash
cd backend
npm install
```

---

### 2️⃣ Configure Environment

Create `.env`:

```env
RPC_URL=http://127.0.0.1:8545
GANACHE_PK=0xyourPrivateKey
PINATA_JWT=your_pinata_jwt
SECRET_KEY=supersecret
PORT=3000
```

---

### 3️⃣ Start Blockchain

Example (Hardhat):

```bash
npx hardhat node
```

(Or use Ganache / Anvil / Geth)

---

### 4️⃣ Run Backend

```bash
npm start
```

Server runs at:

```
http://localhost:3000
```

---

## 📦 Smart Contract

**Traceability.sol** tracks:

* 🌱 Collection events
* 🏭 Processing steps
* 🔬 Quality tests

### Fetch Events

```solidity
function getEvents(string calldata batchId) 
    external view returns (Event[] memory);
```

---

## 🗺 QR & Provenance Tracking

Each batch generates a QR code linking to:

```
/provenance/<batchId>
```

### 📊 Displays:

* Full lifecycle timeline
* Geo-location movement map
* IPFS images & lab reports

---

## 🧪 Testing

```bash
npx hardhat test
```

---

## 📜 License

MIT License — free to use, modify, and distribute.

---

## ❤️ Contributing

Pull requests, feature ideas, and improvements are always welcome!

---
