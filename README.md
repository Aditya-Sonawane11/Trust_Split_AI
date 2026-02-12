# 🚀 TrustSplit AI

**AI-Powered Decentralized Expense Splitter for Students**

Split shared expenses fairly using AI bill parsing and Algorand blockchain settlement with multi-member approval flow.

## 🎯 Problem Statement

College students frequently share expenses (meals, groceries, trips) but struggle with:
- Manual bill calculation errors
- Trust issues in payment settlement
- Disputes over fair splits
- No transparent record keeping

## 💡 Solution

TrustSplit AI combines **AI-powered bill parsing** with **blockchain-based escrow settlement**:

1. **Upload** a bill image via mobile or desktop
2. **AI extracts** merchant, items, and amounts automatically
3. **Smart split** calculates fair distribution (equal, item-based, or custom)
4. **Blockchain escrow** locks funds until all members approve
5. **Auto-settlement** releases payments when threshold reached
6. **Dispute AI** explains split logic in human-readable format

## 🏗 Architecture

```
┌─────────────┐      ┌──────────────┐      ┌─────────────────┐
│   React     │─────▶│  Express.js  │─────▶│   Algorand      │
│   Frontend  │      │   Backend    │      │   Testnet       │
└─────────────┘      └──────────────┘      └─────────────────┘
      │                     │                       │
      │                     ▼                       │
      │              ┌─────────────┐                │
      │              │  AI Layer   │                │
      │              │  OCR + LLM  │                │
      │              └─────────────┘                │
      │                                             │
      └──────────────── Pera Wallet ────────────────┘
```

## 🛠 Tech Stack

- **Frontend**: React + Vite, TailwindCSS, React Router
- **Backend**: Node.js, Express.js, Multer
- **AI**: Tesseract.js (OCR), OpenAI API (parsing)
- **Blockchain**: Algorand SDK (algosdk), Pera Wallet
- **Database**: In-memory (demo) / JSON storage

## 📋 Features

✅ **Bill Upload** - Image upload with preview  
✅ **AI OCR** - Automatic text extraction from receipts  
✅ **Smart Parsing** - Structured JSON extraction (merchant, items, total)  
✅ **Split Calculator** - Equal, item-based, and custom weight splits  
✅ **Wallet Integration** - Real Pera Wallet connection  
✅ **Blockchain Escrow** - Multi-signature approval logic  
✅ **Settlement Flow** - Automatic fund release after approvals  
✅ **Transaction Receipt** - On-chain verification with explorer link  
✅ **Dispute AI** - Explains split calculations in plain English  

## 🚀 Quick Start

### Prerequisites

- Node.js 18+
- npm or yarn
- Pera Wallet mobile app or browser extension
- Algorand testnet account with test ALGO

### Installation

```bash
# Clone repository
git clone <repo-url>
cd trustsplit-ai

# Install backend dependencies
cd backend
npm install

# Install frontend dependencies
cd ../frontend
npm install
```

### Environment Setup

**Backend** - Create `backend/.env`:
```env
PORT=3001
OPENAI_API_KEY=your_openai_api_key_here
ALGORAND_API_TOKEN=
ALGORAND_API_SERVER=https://testnet-api.algonode.cloud
ALGORAND_INDEXER_SERVER=https://testnet-idx.algonode.cloud
```

**Frontend** - Create `frontend/.env`:
```env
VITE_API_URL=http://localhost:3001
VITE_ALGORAND_NETWORK=testnet
```

### Run Development Servers

```bash
# Terminal 1 - Backend
cd backend
npm run dev

# Terminal 2 - Frontend
cd frontend
npm run dev
```

Frontend: http://localhost:5173  
Backend: http://localhost:3001

## 📱 Wallet Setup

1. Install [Pera Wallet](https://perawallet.app/) on mobile or as browser extension
2. Create a new account or import existing
3. Get testnet ALGO from [dispenser](https://bank.testnet.algorand.network/)
4. Connect wallet in TrustSplit AI app

## 🎬 Demo Flow

1. **Landing Page** → Click "Create Expense"
2. **Upload Bill** → Upload sample receipt image
3. **AI Parsing** → View extracted data (merchant, items, total)
4. **Create Group** → Add 2-3 member wallet addresses
5. **Select Split** → Choose equal or item-based split
6. **Preview** → Review amounts per member
7. **Create Escrow** → Connect wallet and create blockchain escrow
8. **Approval Flow** → Members approve via their wallets
9. **Settlement** → Auto-execute when all approve
10. **Receipt** → View transaction hash and explorer link

## 📂 Project Structure

```
trustsplit-ai/
├── backend/
│   ├── server.js              # Express entry point
│   ├── routes/
│   │   ├── bill.routes.js     # Bill upload & parsing endpoints
│   │   ├── split.routes.js    # Split calculation endpoints
│   │   └── expense.routes.js  # Expense & settlement endpoints
│   ├── services/
│   │   ├── ocr.service.js     # Tesseract OCR integration
│   │   ├── ai.service.js      # OpenAI parsing service
│   │   ├── split.service.js   # Split calculation engine
│   │   └── dispute.service.js # AI dispute explainer
│   ├── blockchain/
│   │   ├── client.js          # Algorand client setup
│   │   ├── escrow.js          # Escrow account logic
│   │   ├── transactions.js    # Transaction builders
│   │   └── wallet.js          # Wallet utilities
│   └── package.json
├── frontend/
│   ├── src/
│   │   ├── App.jsx
│   │   ├── pages/
│   │   │   ├── Landing.jsx
│   │   │   ├── UploadBill.jsx
│   │   │   ├── SplitPreview.jsx
│   │   │   ├── GroupApproval.jsx
│   │   │   └── Receipt.jsx
│   │   ├── components/
│   │   │   ├── WalletConnect.jsx
│   │   │   ├── BillUploader.jsx
│   │   │   ├── SplitTable.jsx
│   │   │   └── ApprovalTracker.jsx
│   │   └── utils/
│   │       └── algorand.js
│   └── package.json
├── docs/
│   ├── SETUP.md
│   ├── DEMO.md
│   └── ARCHITECTURE.md
└── README.md
```

## 🧪 Testing

```bash
# Backend tests
cd backend
npm test

# Test split engine
npm run test:split

# Test API endpoints
npm run test:api
```

## 🎓 Hackathon Context

**Track**: Web3 Social Impact / FinTech Innovation

**Problem**: Students lack transparent, trustless expense settlement tools

**Innovation**:
- AI automation reduces manual entry errors
- Blockchain provides immutable settlement records
- Escrow ensures no-one can back out
- Dispute AI builds trust through transparency

**Impact**: Reduces financial friction in student communities, promotes financial literacy, introduces Web3 to everyday use cases

## 🔗 Resources

- [Algorand Testnet Dispenser](https://bank.testnet.algorand.network/)
- [Pera Wallet](https://perawallet.app/)
- [AlgoExplorer Testnet](https://testnet.algoexplorer.io/)
- [Algorand Developer Docs](https://developer.algorand.org/)

## 📄 License

MIT License - Built for educational and hackathon purposes

## 👥 Team

Built with ❤️ for student communities

---

**Demo Mode**: Run with `DEMO_MODE=true` to use mock data without real API calls
