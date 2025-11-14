
##  Project Title

Lancer Protocol - Private Voting System

## Team

Dario Sanchez -
Github: 0xDarioSanchez -
Devfolio: 0xDarioSanchez

Dario Amaya -
Github: Cooldev1337 -
Devfolio: web3path

Cecilia Scarabello -
Github: chinitasca -
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

**Functional MVP:**

Enable on-chain dispute creation, escrow release logic, and commit–reveal voting with a single transaction for judges (they only need to commit).
Deploy on Arbitrum Stylus to demonstrate scalability and low fees.

**Performance Optimization:**

Port at least one module (e.g., reputation or dispute scoring) to Stylus (Arbitrum) for WASM-based execution and gas comparison.

**UX & Frontend:**

Develop a simple dashboard for judges and disputing parties.
Show commit-reveal results and dispute status in real-time.

## Weekly Progress

### Week 1 (ends Oct 31)
**Goals:**

Finalize architecture design (smart contracts + ZK integration flow).

Deploy on local testnet contracts to use as escrow and voting example.

Initialize Stylus development environment (Rust SDK + test contract).

Research ZKM SDK and prepare circuit outline for vote proof.

**Progress Summary:**  


## Week 2 (ends Nov 7)
**Goals:**  
- Implement a basic marketplace and voting contract in Solidity to enable fast testing.  
- Research potential approaches to integrate privacy into the voting process.  
- Begin developing the final project implementation using Arbitrum Stylus.

**Progress Summary:**  
- Completed initial versions of the marketplace and voting contracts in Solidity for rapid testing and validation.  
- Investigated multiple privacy-preserving mechanisms for the voting system, including commit–reveal, threshold encryption, and ZK-based alternatives.  
- Started building the Arbitrum Stylus version of the project to prepare for the final deployment phase.

### Week 2 Code:

https://github.com/0xDarioSanchez/IG-PoC
https://github.com/0xDarioSanchez/IG25-Project

## 🗓️ Week 3 (ends Nov 14)

### Main Repositories Link:

#### Link to main repo with marketplace + protocol integration:

https://github.com/0xDarioSanchez/IG25-Project

#### Link to minimal version for facilitate testing:

https://github.com/0xDarioSanchez/IG25-Protocol

#### Slides / Presentation:
[[Open link]
](https://docs.google.com/presentation/d/1cINF0FIcUCBuz3ttr-vRa_qfe6NkmVh3kzgnmSl77KI/edit?usp=sharing)

**Goals:**

Migrate the voting system from Solidity to Stylus.

Finalize and test the Stylus contracts.

Implement the single-transaction commit–reveal mechanism for basic privacy.

Run end-to-end tests and analyze results to extract technical conclusions.

**Progress Summary:**

Completed the full Stylus implementation of the protocol logic.

Wrote deployment and testing scripts.

Commit–reveal integration and testing is done.

**Summary of Final State**

Over the three weeks, the project reached a fully functional prototype of a privacy-preserving Web3 dispute resolution protocol running on Arbitrum Stylus (Rust).

A complete example marketplace was also developed to demonstrate realistic usage:

Users can open deals and escalate disputes.

Disputes are resolved in the Protocol Contract, where users can register as judges.

Judges participate in private voting using a commit-based scheme.

Implemented Privacy System: Single-Transaction Commit–Reveal

I chose the single-transaction commit–reveal approach because it provides meaningful privacy while keeping the architecture simple and realistic for a short timeframe.

**Key characteristics:**

Judges submit only one commit transaction (hash of vote + nonce).

Votes stay private during the entire commit phase.

When the last commit is submitted, the transaction includes all the nonces, enabling the contract to:

Recompute every hash

Verify all commits

Reveal and tally all votes in the same transaction

The system works entirely on-chain and is 100% functional.

This design removes the usual commit–reveal pain points:

❌ no second transaction

❌ no reveal griefing

❌ no deadline scheduling

❌ no staking required

#### Gas Usage and Performance:

**Reveal Phase (Performed in only one transaction)
**
Judge 1: 82,475 gas 

Judge 2: 67,540 gas

Judge 3: 69,693 gas

Judge 4: 71,870 gas

Other judges average: 69,600 gas

Judge 31: 79,743 gas (higher because it triggers final resolution)

Total: 2,180,618 gas
Average per revealed vote: ~70,340 gas

#### Conclusion

The single-transaction commit–reveal mechanism proves viable and efficient, especially for scenarios needing multiple judges.
With an average cost of ~69.6k gas per revealed vote, this approach scales much better than traditional commit–reveal and avoids the complexities of threshold encryption or ZK circuits.

The contracts are fully implemented, fully functioning, and ready for demo with Stylus.


## 🧾 Learnings
During Invisible Garden 2025 I was able to study and compare different approaches for privacy in on-chain voting (hashed commits, encrypted votes, threshold schemes, and isolated match contracts). I focused especially on the commit–reveal pattern and its variations, and learned how to adapt the mechanism to a single-transaction reveal, synchronizing all judges’ commits at the same moment without requiring multiple steps.

I also learned a lot about developing with Arbitrum Stylus, including how to migrate Solidity logic into Rust-based smart contracts, gas-profiling differences between both environments, and how to structure multi-contract systems (marketplace + protocol) so they interact safely.

Additionally, implementing commit–reveal forced me to think about fairness guarantees, timing assumptions, and griefing resistance—for example, what happens if someone tries to stall the reveal stage, or how to mitigate early-disclosure attacks by generating the commit hash with salted randomness.

Overall, I improved my understanding of privacy-preserving mechanisms, cross-contract design, and practical UX constraints for decentralized dispute resolution.

## Next Steps
My next steps are:

Present the project at upcoming hackathons, showing the marketplace + dispute-resolution prototype working end-to-end with private voting.

Apply for grants to turn this into a full product: a decentralized marketplace that integrates the commit–reveal voting system I built here as a lightweight, efficient resolution layer.

Extend the prototype with features I didn’t have time for, such as vote weighting, optional encryption, judge reputation scoring, and a more user-friendly interface.

Continue optimizing Stylus performance and exploring how far commit–reveal can scale when many votes are required.


_This template is part of the [ARG25 Projects Repository](https://github.com/invisible-garden/arg25-projects)._  
