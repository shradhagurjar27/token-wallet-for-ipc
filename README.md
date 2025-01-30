# Multiuser Ethereum Wallet on ICP

## 🚀 Overview
This multiuser Ethereum wallet allows users to generate an Ethereum address by logging in with their Internet Identity. Users can send and receive Ethereum from other users.

- **Backend:** Rust canister using the `ic-alloy` library to interact with the Ethereum blockchain.
- **Frontend:** Built with React and Vite.
- **Authentication:** Internet Identity for secure login.

🔗 **Live Demo:** [Click here](https://7vics-6yaaa-aaaai-ap7lq-cai.icp0.io)

## 📌 Features
✅ Generate an Ethereum address using Internet Identity login  
✅ Send and receive Ethereum securely  
✅ Fetch ETH balance efficiently via an Ethereum RPC endpoint  
✅ Fast and responsive UI with local state caching  

## 📝 Project Notes
- **Performance Optimization:** Update calls on the IC take 2-3 seconds. To improve UX, the wallet caches the Ethereum address in local state and fetches balances directly from an Ethereum RPC endpoint instead of making costly canister calls.
- **Security:** Private keys are never exposed or stored on-chain.

---

## 🛠️ Setup & Prerequisites
### 🔑 Etherscan API Key
An Etherscan API key is required to query wallet balances. Create an account on [Etherscan](https://etherscan.io/) and add your key to `.env.local`:
```sh
echo "VITE_ETHERSCAN_API_KEY=YOUR_API_KEY" > .env.local
```

### 🏗️ Dev Environment Setup

**Prerequisites:**
- Local Internet Computer Dev Environment
- `pnpm`

Clone the repository and install dependencies:
```sh
git clone https://github.com/your-repo.git
cd your-repo
pnpm install
```

## 🚀 Running the Project
1. **Start the Internet Computer**
   ```sh
   dfx start --background
   ```
2. **Install dependencies**
   ```sh
   pnpm install
   ```
3. **Deploy the Canisters**
   ```sh
   dfx deploy
   ```
4. **Run the Frontend (Hot Reloading)**
   ```sh
   pnpm run dev
   ```

---

## 📡 Backend Canister Methods
### 🏷️ `get_address`
Fetches the Ethereum address for a given principal.
```sh
dfx canister call backend get_address
```
Retrieve for a specific principal:
```sh
dfx canister call backend get_address '(opt principal "your-principal-id")'
```

### 💰 `get_balance`
Returns the ETH balance of a principal's Ethereum address.
```sh
dfx canister call backend get_balance
```
For a specified principal:
```sh
dfx canister call backend get_balance '(opt principal "your-principal-id")'
```

### 📤 `send_eth`
Sends ETH from the user's Ethereum address to another.
```sh
dfx canister call backend send_eth '("0xRecipientAddress", 1)'
```

---

## 📜 License
This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for more details.

## 🤝 Contributing
Contributions are welcome! Please open an issue or submit a pull request if you have any suggestions or improvements.

💡 **Tip:** Use this repository as a starting point for building your own multiuser Ethereum wallet on the Internet Computer.

---

⭐ **Star this repo if you found it useful!** 🚀

