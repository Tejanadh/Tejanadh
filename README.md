# Tejanadh 🛡️
### Smart Contract Security Researcher & Systems Auditor (EVM + Solana)

B.Tech Computer Science student (Graduating 2028) & Independent Web3 Security Researcher. I specialize in finding critical vulnerabilities in low-level systems (C/Rust) and complex DeFi protocols (Solidity).

[Twitter/X](https://x.com/TEJANadh10) | [LinkedIn](https://linkedin.com/in/teja-nadh-2919062b4) | tejanadh927@gmail.com

---

## 🏆 Key Critical & High Disclosures
Below is a summary of major protocol vulnerabilities I have independently identified, responsibly disclosed, and written deterministic Proofs of Concept (PoCs) for:

| Protocol / Standard | Severity | Bug Vector | Impact | Proof of Concept |
| :--- | :---: | :--- | :--- | :--- |
| **Firedancer (Jump Crypto)** | **Critical** | Zero-Click Remote Out-of-Bounds Write in Gossip Deserializer | Potential validator network hijack | [Private/Disclosed](https://github.com/Tejanadh/firedancer-gossip-rce-research) |
| **Kamino Finance** | **Critical** | Oracle Timestamp Forgery | Put $100M+ JLP collateral at risk | [Repo Link](https://github.com/Tejanadh/kamino-security-research) |
| **ERC-4337 EntryPoint v0.8.0** | **Critical** | Gas accounting flaw in Post-Op phase | Paymaster stake drain ($2.8M+ TVL) | [Repo Link](https://github.com/Tejanadh/entrypoint-poc) |
| **Ethena Minting V2** | **High** | Type Truncation (`uint128` to `uint64`) in `verifyNonce` | Permanent mint/redeem DoS | [Repo Link](https://github.com/Tejanadh/ethena-nonce-truncation-dos) |
| **1inch Solana Bridge** | **High** | Rescue Mechanism Access Control Bypass | Permanent fund theft vector | [Repo Link](https://github.com/Tejanadh/1inch-solana-rescue-theft-research) |
| **Symbiotic** | **Critical** | Phantom Debt in Shared Vaults (`BaseSlasher`) | Slashing logic breakdown | [Repo Link](https://github.com/Tejanadh/symbiotic-critical-research) |
| **Hyperbridge** | **Critical** | Cross-chain signature replay & token inflation | Arbitrary minting of asset tokens | [Repo Link](https://github.com/Tejanadh/hyperbridge-security-research) |
| **DeXe Governance** | **High** | Double-Voting Power via Missing Stake Check | Governance takeover vector | [Repo Link](https://github.com/Tejanadh/dexe-gov-bug-report) |

---

## 🛠️ Tech Stack & Skills
- **Languages:** Rust, Solidity, C, Go, TypeScript
- **Frameworks & Tools:** Foundry, Anchor, Hardhat, solana-test-validator, GDB, Valgrind, Echidna
- **Areas of Research:** Oracle manipulation, restaking slashing mechanics, cross-chain bridge security, gas accounting, EVM/Solana runtime quirks, memory corruption in protocol clients.
