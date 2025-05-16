# 🚀 Latio Travel Sync — Cross-Border Payments and Travel Optimization on Stellar
Latio Travel Sync is a Stellar-based cross-border payment platform designed for international travelers and LATAM locals, enabling seamless global payments, travel planning, and AI-driven recommendations with real-time synchronization to the blockchain and Firestore.

🌐 Live Demo:
https://latio-travel-sync-guur.vercel.app/
🎥 Demo Video:
https://www.loom.com/share/88fd0313d6494c3f82a41da2a684e9fb?sid=9612f2c0-cb78-4419-a67c-b69beec6d1e8

# 📸 Screenshots:
dashboard
![image](https://github.com/user-attachments/assets/fd7bb638-8127-4122-bb12-a1c598f1c076)
wallet
![image](https://github.com/user-attachments/assets/5c22a034-f906-4051-ad10-3afa6f980d10)


Travel Planner — Coming Soon!

Transaction Assignment to Travel Plans — Coming Soon!

AI Travel Recommendations — Coming Soon!

📖 Project Overview:
Latio is designed with two main user groups in mind:

International Travelers: For instant, low-cost currency exchange.

LATAM Locals: For seamless global payments and travel optimization.

Key Features:

📱 Passkey Kit Authentication: Secure, passwordless wallet connection.

🌐 Stellar Blockchain Integration: Real-time transactions and synchronization.

💳 Travel Planner: Plan and budget trips, synced with blockchain payments.

🤖 AI Recommendations: Personalized travel suggestions using Google AI Studio.

🔗 Firestore Synchronization: Persistent travel plans and transaction history.

🏗️ Project Structure:
less
```
src/
├── api/
│   ├── googleAI.ts            // AI travel recommendations using Google AI Studio
│   ├── stellarContract.ts     // Interactions with Stellar blockchain
│   └── firebaseCRUD.ts        // Firestore CRUD operations for travel and transactions
│
├── components/
│   ├── layout/
│   │   ├── page-container.tsx
│   │   └── navbar.tsx
│   ├── modules/
│   │   ├── wallet/
│   │   │   ├── WalletOverview.tsx
│   │   │   └── TransactionList.tsx
│   │   ├── travel/
│   │   │   ├── TravelCard.tsx
│   │   │   ├── TravelForm.tsx
│   │   │   └── TravelDetails.tsx
│   │   └── recommendations/
│   │       ├── Recommendations.tsx
│   │       └── RecommendationModal.tsx
│   └── ui/
│       ├── button.tsx
│       ├── card.tsx
│       └── tabs.tsx
│
├── pages/
│   ├── Wallet.tsx
│   ├── Travel.tsx
│   ├── TravelDetails.tsx
│   └── Recommendations.tsx
│
├── store/
│   └── useStore.ts             // Global state management with Zustand
│
└── types/
    └── wallet.ts               // Type definitions for transactions and balances
```
# 🔗 Blockchain Interaction:
Wallet Connection:

Powered by PasskeyKit for passwordless authentication.

Users connect their wallet and it generates a Stellar address (Soroban Contract Address: "C...").

Transaction Handling:

Transactions are sent using Stellar Smart Contracts (Soroban).

For traditional Stellar accounts ("G..."), we interact with the Horizon API.

Transactions are automatically recorded in Firestore, linked to specific travel plans if the user selects one.

Real-time Sync:

Balances are fetched and displayed in the wallet interface.

Stellar transactions are listened to in real-time using Horizon and Firestore subscriptions.


## 📡 Stellar Contract Interaction:
We interact with two different types of addresses:

"G..." → Traditional Stellar Wallets

"C..." → Soroban Smart Contracts

Sending Payments:
```
await sendStellarPayment(
  {
    destination: "GXXXXXXX...YYYY",
    amount: "10",
    memo: "Payment for Travel Booking",
  },
  walletAddress,
  secretKey
);
Fetching Balance:
typescript
Copy
Edit
const balance = await getStellarBalance(walletAddress);
console.log("💰 Current Balance: ", balance);
```
Fetching Transaction History:
```
const history = await fetchTransactionHistory(walletAddress, 5);
console.log("🔄 Transaction History: ", history);
```
## 🤖 AI-Powered Travel Recommendations:
Powered by Google AI Studio, we fetch real-time travel insights:

Top attractions

Local cuisines

Budget tips

Safety considerations

Transportation options

```
const recommendations = await generateTravelRecommendations({
  location: "Berlin",
  budget: 500,
  duration: 7,
  preferences: ["food", "local culture"]
});
console.log(recommendations);
```
🔥 How to Run the Project:
Clone the repository:
```
git clone https://github.com/your-username/latio-travel-sync.git
```
Navigate into the project directory:

```
cd latio-travel-sync
```
Install dependencies:

```
npm install
```
Set up environment variables (.env):

```
VITE_GOOGLE_GENAI_API_KEY=<Your Google AI API Key>
VITE_RPC_URL=https://rpc-testnet.stellar.org
VITE_NETWORK_PASSPHRASE="Test SDF Network ; September 2015"
```
Start the application:
```
npm run dev
```
Access the application at:
http://localhost:5173

📚 Documentation:
For detailed documentation on both Product and Engineering, visit:
🔗 Curated Documentation for Latio Travel Sync

✨ Next Steps:
Screenshots for Each Module — Coming Soon.

Deploy to Production — Deployment pending.

Complete Firestore Sync for Transactions — In progress.
