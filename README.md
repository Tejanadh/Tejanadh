# Tejanadh

**Smart Contract Security Researcher | Solana + Ethereum**

Independent researcher focused on low-level systems (Rust/Solana) and DeFi protocols (Solidity). I build deterministic PoCs, verify claims on live RPC / mainnet forks, and prefer honest severity over inflated Crits.

[Twitter](https://x.com/TEJANadh10) · [LinkedIn](https://linkedin.com/in/teja-nadh-2919062b4) · [Email](mailto:tejanadh927@gmail.com)

---

## Selected findings (honest severity)

Severities below are **research framing**, not bounty payout decisions. Links go to public writeups / PoCs.

| Protocol | Severity | Finding | What is proven | PoC / writeup |
|----------|----------|---------|----------------|---------------|
| **ERC-4337 EntryPoint v0.8** | **Critical** | On `postOp` OOG failure, EntryPoint charges paymasters for internal overhead **beyond** `paymasterPostOpGasLimit` (EIP-4337 §4.3.1 upper bound) — including empty `postOp` | Foundry PoCs (empty postOp, bundle, Safe 4337 module); fix PR capping OOG overhead | [Repo](https://github.com/Tejanadh/entrypoint-poc) · [Fix PR](https://github.com/Tejanadh/account-abstraction/pull/1) |
| **Kamino / Scope** | **High** | Derived oracles (JLP, Jito VRT) stamp `DatedPrice` with refresh-time `Clock`, not source observation time — defeats KLend age checks after permissionless refresh | Public Scope + KLend source; live RPC vault slot lag | [Repo](https://github.com/Tejanadh/kamino-security-research) |
| **DEXE Governance** | **High** | `delegateTokens` missing `ifNotStaken` while stake/withdraw enforce it → stake + delegate double-use of voting power | Source modifier gap + Hardhat path | [Repo](https://github.com/Tejanadh/dexe-gov-bug-report) |
| **Symbiotic BaseSlasher** | **High** | Slash path ignores `Vault.onSlash` return → phantom cumulative slash / shared-vault accounting desync | Foundry-style accounting repro; disclosed (disputed path) | [Repo](https://github.com/Tejanadh/symbiotic-critical-research) |
| **1inch Solana** | **High (privileged)** | `rescue_funds_for_order` path issues after order close (delay / recipient) | Anchor-style PoC; **requires whitelisted resolver**, not arbitrary caller | [Repo](https://github.com/Tejanadh/1inch-solana-rescue-theft-research) |
| **Jupiter Lend** | **Medium–High (design risk)** | Asymmetric oracle max-age: user ops fail at 600s while liquidations continue to 7200s | Program constants + fork scripts; may be intentional | [Repo](https://github.com/Tejanadh/jupiter-lend-oracle-asymmetry) |
| **Ethena Minting V2** | **Latent / Medium** | `verifyNonce` truncates `uint128` → `uint64` for bitmap slot; `N` and `N+2^64` collide | Live `verifyNonce` collision; **not currently exploitable at observed nonce scale** | [Repo](https://github.com/Tejanadh/ethena-nonce-truncation-dos) |
| **Hyperbridge** | **Research (unverified on prod path)** | Decimal scaling / replay / fee / timeout hypotheses | Offline logic sims — **not claimed as confirmed production Crits** | [Repo](https://github.com/Tejanadh/hyperbridge-security-research) |
| **EigenDA** | **Research (no Critical)** | `confirmBatch` header-trust seam + cert/orbit census | 59+ fork tests; production paths fail-closed / mitigated in known consumers | [Repo](https://github.com/Tejanadh/eigenda-security-research) |

> Additional work may be under private coordinated disclosure / bounty programs and is not listed until publication is allowed.

---

## How I work

- **Root cause first** — source line + invariant, not tool spam  
- **Honest PoCs** — live RPC / fork tests; no staged “exploit success” logs  
- **Severity discipline** — privilege, reachability, and current exploitability stated up front  
- **Stack:** Rust (Solana), Solidity, Foundry, Anchor, Hardhat, mainnet forks  

---

## Skills

| Area | Stack |
|------|--------|
| Languages | Rust, Solidity, C |
| Tooling | Foundry, Anchor, Hardhat, solana-test-validator, Echidna |
| Domains | Oracles & liveness, lending/liquidation, restaking, governance, AA / ERC-4337, bridges |

---

## About

B.Tech Computer Science ~2 years independent smart contract security research across Solana and Ethereum.

**Open to:** remote Smart Contract Security Researcher / Auditor roles — full-time, part-time, or internship — with audit firms and protocols that care about rigorous, reproducible work.

---

*Responsible disclosure first. Public material is only for issues already reported or explicitly safe to publish.*
