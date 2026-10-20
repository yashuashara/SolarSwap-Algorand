# ☀️ SolarSwap — P2P Renewable Energy Trading on Algorand

A decentralized marketplace where households with rooftop solar panels can sell surplus energy directly to their neighbours, settled on the **Algorand** blockchain.

> 🚧 **Status:** In active development as part of the *Algorand Blockchain Application Developer* course (FutureSkills Prime).

---

## 📌 Problem

- Small solar producers usually sell excess power back to the grid at low feed-in rates.
- Consumers pay full utility prices even when cleaner energy is being produced next door.
- Centralized intermediaries add cost and make the pricing and settlement process hard to see.

## 💡 Solution

SolarSwap lets **prosumers** (producers + consumers) trade energy peer-to-peer:

1. Verified energy surplus is tokenized as an **Algorand Standard Asset (ASA)**, where 1 token = 1 kWh.
2. Sellers list energy at their own price, and buyers purchase directly.
3. A smart contract settles each trade **atomically**: the energy tokens and the ALGO payment move together, or the trade does not happen.
4. Every trade is recorded on-chain, so it is transparent and auditable.

## ⚙️ Why Algorand?

| Feature | Benefit for energy trading |
|---|---|
| **Low, fixed fees** (~0.001 ALGO) | Makes small, frequent kWh trades affordable |
| **~3s finality** | Trades settle almost instantly |
| **Algorand Standard Assets** | Native energy tokens without writing a token contract |
| **Atomic transfers** | Payment and energy delivery succeed or fail together |
| **Carbon-negative network** | Fits a green-energy use case |

## 🏗️ Planned Architecture

```
[Smart Meter / Mock Data] ──► [Backend API] ──► mints kWh tokens (ASA)
                                                    │
[React Frontend + Pera Wallet] ◄──► [Marketplace Smart Contract (Algorand)]
        list offer / buy energy        escrow + atomic settlement
```

## 🛠️ Tech Stack

- **Smart contracts:** Algorand Python (Puya) / PyTeal
- **Tooling:** AlgoKit, AlgoKit Utils
- **Local network:** AlgoKit LocalNet → TestNet
- **Frontend:** React + TypeScript
- **Wallet:** Pera Wallet (via `@txnlab/use-wallet`)
- **Backend:** Node.js / Express (meter data simulation)

## 🗺️ Roadmap

- [x] Project idea and repository setup
- [ ] Set up AlgoKit project and LocalNet
- [ ] Create the energy token (ASA)
- [ ] Write the marketplace smart contract (list, buy, cancel)
- [ ] Implement atomic settlement for trades
- [ ] Build the React frontend with wallet connection
- [ ] Simulate smart-meter data
- [ ] Deploy to Algorand TestNet
- [ ] Testing and documentation

## 🚀 Getting Started

> Setup instructions will be added as the project develops.

```bash
# Prerequisites: Python 3.12+, Docker, AlgoKit
pipx install algokit
git clone https://github.com/<your-username>/solarswap-algorand.git
cd solarswap-algorand
algokit localnet start
```

## 👩‍💻 Author

**Yashvi Ashara**, M.Sc Blockchain Technology, MIT-WPU Pune

## 📄 License

MIT
