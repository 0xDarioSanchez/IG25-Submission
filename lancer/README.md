IWANTTODEMO

##  Project Title

Lancer Protocol - Private Voting System

## Team

Dario Sanchez
Github: 0xDarioSanchez
Devfolio: 0xDarioSanchez

Dario Amaya
Github: Cooldev1337
Devfolio: web3path

Cecilia Scarabello
Github: chinitasca
Devfolio: CeciSca 


## Project Description

Lancer Protocol is a decentralized dispute-resolution layer for Web3 marketplaces.
It enables fair, transparent, and censorship-resistant arbitration between freelancers and clients through a network of independent on-chain judges.
Judges are economically incentivized via a reputation and reward mechanism based on game theory, ensuring that truthful voting is the most rational behavior.

However, full transparency on-chain introduces two risks: bribery of visible judges and biased voting due to observable majority trends.
Lancer solves these using commit–reveal and zero-knowledge (ZK) privacy layers — keeping votes secret until finalized and preventing manipulation.

## Tech Stack

Smart Contracts: Solidity, Rust (via Arbitrum Stylus)

Blockchain Infrastructure: Ethereum Sepolia testnet, AltLayer Rollup (RaaS), ZKM zkVM verifier

ZK Tools: Circom / Noir for proof circuits (vote validity + identity protection)

Front-End: Next.js + TypeScript + Tailwind

Backend & APIs: Node.js, Wagmi, Ethers.js

Storage: IPFS / Web3.Storage for dispute evidence

Wallet Integration: MetaMask, WalletConnect

DevOps: Foundry, Vercel for web deployment

Optional Integrations: World ID or Sismo for ZK judge identity

## Objectives

Functional MVP:

Enable on-chain dispute creation, commit–reveal voting, and escrow release logic.
Deploy on an AltLayer rollup to demonstrate scalability and low fees.

Privacy Prototype:

Integrate a ZKM zkVM proof verifier to validate vote integrity without revealing judge choices.
Build a small Noir circuit for vote validity proof.

Performance Optimization:

Port at least one module (e.g., reputation or dispute scoring) to Stylus (Arbitrum) for WASM-based execution and gas comparison.

UX & Frontend:

Develop a simple dashboard for judges and disputing parties.
Show ZK-proof verification results and dispute status in real-time.

## Weekly Progress

### Week 1 (ends Oct 31)
**Goals:**

Finalize architecture design (smart contracts + ZK integration flow).

Deploy on local testnet contracts to use as escrow and voting example.

Initialize Stylus development environment (Rust SDK + test contract).

Research ZKM SDK and prepare circuit outline for vote proof.

**Progress Summary:**  


### Week 2 (ends Nov 7)
**Goals:**  
- Implement a basic marketplace and voting contract in Solidity to enable fast testing.  
- Research potential approaches to integrate privacy into the voting process.  
- Begin developing the final project implementation using Arbitrum Stylus.

**Progress Summary:**  
- Completed initial versions of the marketplace and voting contracts in Solidity for rapid testing and validation.  
- Investigated multiple privacy-preserving mechanisms for the voting system, including commit–reveal, threshold encryption, and ZK-based alternatives.  
- Started building the Arbitrum Stylus version of the project to prepare for the final deployment phase.

### Solidity Code:

https://github.com/0xDarioSanchez/IG-PoC

### Stylus Code:

https://github.com/0xDarioSanchez/IG25-Project

🗓️ Week 3 (ends Nov 14)

**Goals:
**
Migrate the voting system from Solidity to Stylus.

Finalize and test the Stylus contracts.

Implement the single-transaction commit–reveal mechanism for basic privacy.

Run end-to-end tests and analyze results to extract technical conclusions.

**Progress Summary:
**
Completed the full Stylus implementation of the protocol logic.

Wrote deployment and testing scripts.

Commit–reveal integration and testing still pending.

## Final Wrap-Up
_After Week 3, summarize your final state: deliverables, repo links, and outcomes._

- **Main Repository Link:**  
- **Demo / Deployment Link (if any):**  
- **Slides / Presentation (if any):**



## 🧾 Learnings
_What did you learn or improve during ARG25?_



## Next Steps
_If you plan to continue development beyond ARG25, what’s next?_



_This template is part of the [ARG25 Projects Repository](https://github.com/invisible-garden/arg25-projects)._  
_Update this file weekly by committing and pushing to your fork, then raising a PR at the end of each week._
