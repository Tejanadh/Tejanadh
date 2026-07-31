# Tejanadh

**Smart Contract Security Researcher | Solana + Ethereum**

Independent researcher specializing in low-level systems (Rust/Solana) and complex DeFi protocols (Solidity). I build deterministic PoCs on mainnet forks and work with core teams on fixes.

[Twitter](https://x.com/TEJANadh10) · [LinkedIn](https://linkedin.com/in/teja-nadh-2919062b4) · [Email](mailto:tejanadh927@gmail.com)

---

## Selected Findings & PoCs

| Protocol | Severity | Finding | Impact | PoC |
|----------|----------|---------|--------|-----|
| **Kamino Finance** | Critical | Oracle timestamp liveness bypass | $100M+ JLP collateral at risk | [Repo](https://github.com/Tejanadh/kamino-security-research) |
| **ERC-4337 EntryPoint v0.8** | Critical | Gas accounting flaw in `postOp` | Paymaster stake drain (~$2.8M TVL at risk) | [Repo](https://github.com/Tejanadh/entrypoint-poc) |
| **Symbiotic BaseSlasher** | High / Critical | Phantom debt creation in shared vaults | Breaks slashing guarantees (live at report) | [Repo](https://github.com/Tejanadh/symbiotic-critical-research) |
| **Hyperbridge** | Critical / High | Token inflation (`10¹²×`) + cross-chain signature replay | Arbitrary minting / replay across chains | [Repo](https://github.com/Tejanadh/hyperbridge-security-research) |
| **1inch Solana** | High | `rescue_funds` bypass | Unauthorized fund recovery path | [Repo](https://github.com/Tejanadh/1inch-solana-rescue-theft-research) |
| **DEXE Governance** | High | Double-voting power escalation | Governance power inflation | [Repo](https://github.com/Tejanadh/dexe-gov-bug-report) |
| **Jupiter Lend** | High | Oracle staleness asymmetry | Users locked out while liquidations continue | [Repo](https://github.com/Tejanadh/jupiter-lend-oracle-asymmetry) |
| **Ethena Minting V2** | High | Nonce truncation collision DoS | Permanent mint/redeem DoS for affected nonces | [Repo](https://github.com/Tejanadh/ethena-nonce-truncation-dos) |
| **EigenDA** | Research | `confirmBatch` header-trust + cert/orbit census | 59+ fork PoCs; production paths fail-closed | [Repo](https://github.com/Tejanadh/eigenda-security-research) |

> Additional private disclosures under coordinated / bounty programs (not public until allowed).

---

## What I bring

- **Rust (Solana)** + **Solidity (EVM)** — end-to-end exploit reasoning, not just tool output
- **Deterministic PoCs** on mainnet forks: Foundry, Anchor, `solana-test-validator`
- **Focus areas:** oracles & liveness, gas accounting, cross-chain messaging, liquidation/margin math, governance edge cases
- **Process:** root-cause writeups, impact quantification, fix collaboration with protocol teams

---

## Skills

| Area | Stack |
|------|--------|
| Languages | Rust, Solidity, C |
| Tooling | Foundry, Anchor, Hardhat, solana-test-validator, Echidna, GDB |
| Domains | DeFi (lending, perps, restaking), AA / ERC-4337, bridges, Solana programs |

---

## About

B.Tech Computer Science (graduating 2028). ~2 years independent smart contract security research with multiple high/critical findings across production Solana and Ethereum protocols.

**Open to:** remote Smart Contract Security Researcher / Auditor roles — full-time, part-time, or internship — with top-tier audit firms and protocols.

---

*Responsible disclosure first. Public PoCs are only for issues already reported (and, where required, approved for publication).*
