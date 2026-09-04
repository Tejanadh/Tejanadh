<h1 align="center">Tejanadh</h1>
<p align="center"><b>Smart Contract Security Researcher — Solana + Ethereum</b></p>

<p align="center">
  <img src="https://img.shields.io/badge/Solidity-363636?logo=solidity&logoColor=white" />
  <img src="https://img.shields.io/badge/Rust-000000?logo=rust&logoColor=white" />
  <img src="https://img.shields.io/badge/Foundry-1C1C1C" />
  <img src="https://img.shields.io/badge/Anchor-512BD4" />
  <img src="https://img.shields.io/badge/Solana-9945FF?logo=solana&logoColor=white" />
  <img src="https://img.shields.io/badge/Ethereum-3C3C3D?logo=ethereum&logoColor=white" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Open%20to-Security%20Researcher%20%2F%20Auditor%20roles-2ea44f" />
  <img src="https://komarev.com/ghpvc/?username=Tejanadh&style=flat&color=blue&label=profile+views" />
</p>

Independent researcher focused on **low-level systems (Rust / Solana)** and **DeFi protocol logic (Solidity)**. I build deterministic PoCs, verify claims on live RPC / mainnet forks, and prefer **honest severity over inflated criticals**.

<p align="center">
  <a href="https://x.com/TEJANadh10">Twitter / X</a> ·
  <a href="https://linkedin.com/in/teja-nadh-2919062b4">LinkedIn</a> ·
  <a href="mailto:tejanadh927@gmail.com">Email</a>
</p>

<p align="center">
  📂 <b><a href="https://github.com/Tejanadh/audit-portfolio">Full audit portfolio & findings index →</a></b>
</p>

---

## 🔬 Currently

- Independent security research across **Solana and Ethereum** DeFi.
- Active in private **audit competitions and coordinated-disclosure programs** — several findings are under embargo and are published here only once results are public.
- Building depth in async vault accounting, oracle liveness, and restaking/bridge money-paths.

---

## 🎯 Selected findings

> Severities below are **research framing**, not bounty payout decisions. Links go to public writeups / PoCs. Work under active embargo is withheld until publication is permitted.

| Protocol | Severity | Finding | What is proven | Link |
|----------|----------|---------|----------------|------|
| **ERC-4337 EntryPoint v0.8** | **Critical** | On `postOp` OOG failure, EntryPoint charges paymasters for internal overhead **beyond** `paymasterPostOpGasLimit` (EIP-4337 §4.3.1 upper bound), including an empty `postOp` | Foundry PoCs (empty postOp, bundle, Safe 4337 module) + fix PR capping OOG overhead | [Repo](https://github.com/Tejanadh/entrypoint-poc) · [Fix PR](https://github.com/Tejanadh/account-abstraction/pull/1) |
| **Kamino / Scope** | **High** | Derived oracles (JLP, Jito VRT) stamp `DatedPrice` with refresh-time `Clock`, not source observation time — defeats KLend age checks after a permissionless refresh | Public Scope + KLend source; live RPC vault-slot lag | [Repo](https://github.com/Tejanadh/kamino-security-research) |
| **DEXE Governance** | **High** | `delegateTokens` missing the `ifNotStaken` guard that stake/withdraw enforce → stake + delegate double-use of voting power | Source modifier gap + Hardhat repro | [Repo](https://github.com/Tejanadh/dexe-gov-bug-report) |
| **Symbiotic BaseSlasher** | **High** | Slash path ignores `Vault.onSlash` return → phantom cumulative slash / shared-vault accounting desync | Foundry-style accounting repro; disclosed (disputed path) | [Repo](https://github.com/Tejanadh/symbiotic-critical-research) |
| **1inch Solana** | **High (privileged)** | `rescue_funds_for_order` path issues after order close (delay / recipient) | Anchor PoC — **requires whitelisted resolver**, not arbitrary caller | [Repo](https://github.com/Tejanadh/1inch-solana-rescue-theft-research) |
| **Jupiter Lend** | **Medium–High (design risk)** | Asymmetric oracle max-age: user ops fail at 600s while liquidations continue to 7200s | Program constants + fork scripts; may be intentional | [Repo](https://github.com/Tejanadh/jupiter-lend-oracle-asymmetry) |
| **Ethena Minting V2** | **Latent / Medium** | `verifyNonce` truncates `uint128` → `uint64` for the bitmap slot; `N` and `N + 2^64` collide | Live `verifyNonce` collision; **not currently exploitable at observed nonce scale** | [Repo](https://github.com/Tejanadh/ethena-nonce-truncation-dos) |
| **EigenDA** | **Research (no Critical)** | `confirmBatch` header-trust seam + cert/orbit census | 59+ fork tests; production paths fail-closed / mitigated in known consumers | [Repo](https://github.com/Tejanadh/eigenda-security-research) |
| **Hyperbridge** | **Research (unverified on prod path)** | Decimal-scaling / replay / fee / timeout hypotheses | Offline logic sims — **not claimed as confirmed production criticals** | [Repo](https://github.com/Tejanadh/hyperbridge-security-research) |
| **Base L1 — Azul** | **Verified safe** | `AggregateVerifier` multi-proof census | 23 mainnet-fork tests confirm fail-closed behaviour — **no vulnerability disclosed** | [Repo](https://github.com/Tejanadh/azul-multi-proof-analysis) |

> Additional work is under private coordinated disclosure / bounty programs and is not listed until publication is allowed.

---

## 🏅 Recognition & disclosures

- **Symbiotic** — accounting-desync finding **responsibly disclosed via Cantina (#292)**.
- **ERC-4337 EntryPoint** — reproduced an EIP-spec-violating paymaster overcharge with a **fix PR**, cross-checked against the **Safe 4337 Module**.
- Active in **Immunefi audit competitions** and **private coordinated-disclosure** programs (embargoed findings published once results are public).

---

## 🧭 How I work

- **Root cause first** — the source line and the broken invariant, not tool spam.
- **Honest PoCs** — live RPC / mainnet-fork tests; no staged "exploit success" logs.
- **Severity discipline** — privilege, reachability, and *current* exploitability stated up front.
- **Negative results count** — I document what I verified *safe* (e.g. Azul), because knowing a path is fail-closed is worth as much as a finding.

---

## 🛠 Stack

| Area | Tools |
|------|-------|
| **Languages** | Rust, Solidity, C |
| **Tooling** | Foundry, Anchor, Hardhat, `solana-test-validator`, Echidna, mainnet forks |
| **Domains** | Oracles & liveness · lending / liquidation · restaking · governance · account abstraction (ERC-4337) · bridges · data availability |

---

## 👤 About

B.Tech Computer Science · ~2 years of independent smart contract security research across Solana and Ethereum.

**Open to:** remote **Smart Contract Security Researcher / Auditor** roles — full-time, part-time, or internship — with audit firms and protocols that value rigorous, reproducible work.

---

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Tejanadh&layout=compact&langs_count=8&hide_border=true&theme=vue&exclude_repo=firedancer,scope,account-abstraction,ube,DeXe-Protocol,30-Days-of-C,project-based-learning" alt="Top languages" />
</p>

<sub>Responsible disclosure first. Public material covers only issues already reported or explicitly safe to publish.</sub>
