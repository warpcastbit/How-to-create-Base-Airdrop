# How to Build Base Airdrop

A step-by-step guide for creating and deploying a random token airdrop contract on the **Base network** using Solidity 0.8.30 and Remix IDE.  

This repository contains the Solidity contract and full instructions for deployment, verification, and usage.  

---

## 📌 Overview
The **BaseAirdrop** contract is an ERC-20 compatible token with built-in random airdrop functionality.  
- Total supply: **5,000,000 BAIR** (18 decimals)  
- Tokens are initially held by the contract itself  
- Users can claim a random amount of tokens between **100 – 50,000** units (scaled by decimals)  
- A percentage reward (default **5%**) is automatically given to the owner for every claim  
- Owner can withdraw remaining tokens, pause claims, and update parameters  

---

## ✨ Features
- ✅ ERC-20 standard functions (`transfer`, `approve`, `transferFrom`)  
- 🎲 Randomized claim amounts per user  
- 🏦 Automatic owner reward (configurable, up to 20%)  
- 🔒 Claim pause/resume control  
- ⚙️ Adjustable min/max claim ranges  
- 📤 Withdraw leftover tokens (partial or all)  

---

## 🛠 Requirements
- Browser with [Remix IDE](https://remix.ethereum.org)  
- Wallet supporting **Base network** (e.g. [OKX Wallet](https://www.okx.com/), [MetaMask](https://metamask.io/))  
- Base Mainnet RPC configured in your wallet  

---

## 🚀 Deployment Using Remix IDE

1. Open [Remix IDE](https://remix.ethereum.org) in your browser.  
2. Create a new file `BaseAirdrop.sol` and paste the **BaseAirdrop contract code**.  
3. Compile the contract:
   - Compiler: **Solidity 0.8.30**
   - Optimization: **Enabled**
   - Runs: **200**  
4. Connect your wallet (Injected Web3) and select **Base Mainnet** network.  
5. Deploy the contract from the **Deploy & Run Transactions** panel.  
6. Confirm the transaction in your wallet.  

---

## 🔎 Verification on BaseScan
1. Go to [BaseScan Verify](https://basescan.org/verifyContract).  
2. Enter your deployed contract address.  
3. Select **Solidity (Single file)**.  
4. Set compiler version: `0.8.30`  
5. Enable optimization and set runs to `200`.  
6. Paste the full contract code (`BaseAirdrop.sol`).  
7. Submit and wait for confirmation.  

---

## 🎮 Usage

### Claim Tokens
- Any user can call `claimRandom()` from their wallet.  
- The user receives a random amount of tokens, and the owner automatically receives the reward percentage.  

### Owner Functions
- **Withdraw remaining tokens:**  
```solidity
withdrawTokens(amount)
withdrawAllTokens()
 
