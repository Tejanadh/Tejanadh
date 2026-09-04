<h1 align="center">Tejanadh</h1>
<p align="center"><b>Smart Contract Security Researcher · Solana + Ethereum</b></p>
<p align="center"><i>If I can't make it break in a test, I don't claim it breaks.</i></p>

<p align="center">
  <img src="https://img.shields.io/badge/Solidity-363636?logo=solidity&logoColor=white" />
  <img src="https://img.shields.io/badge/Rust-000000?logo=rust&logoColor=white" />
  <img src="https://img.shields.io/badge/Foundry-1C1C1C" />
  <img src="https://img.shields.io/badge/Anchor-512BD4" />
  <img src="https://img.shields.io/badge/Solana-9945FF?logo=solana&logoColor=white" />
  <img src="https://img.shields.io/badge/Ethereum-3C3C3D?logo=ethereum&logoColor=white" />
</p>

<p align="center">
  <a href="https://x.com/TEJANadh10"><img src="https://img.shields.io/badge/X-@TEJANadh10-000000?style=for-the-badge&logo=x" /></a>
  <a href="https://linkedin.com/in/teja-nadh-2919062b4"><img src="https://img.shields.io/badge/LinkedIn-Teja%20Nadh-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
  <a href="mailto:tejanadh927@gmail.com"><img src="https://img.shields.io/badge/Email-tejanadh927-D14836?style=for-the-badge&logo=gmail&logoColor=white" /></a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Open%20to-Security%20Researcher%20%2F%20Auditor%20roles-2ea44f?style=for-the-badge" />
  <img src="https://komarev.com/ghpvc/?username=Tejanadh&style=for-the-badge&color=blue&label=views" />
</p>

Independent researcher working across **Solana (Rust/Anchor)** and **Ethereum (Solidity)**. I focus on the structural soundness of DeFi — oracle integrity, vault/share accounting, lending and liquidation math, restaking, account abstraction, and the cross-contract interactions that turn a benign-looking write into a ledger break. I build **deterministic PoCs on live RPC / mainnet forks**, and I report **honest severity over inflated criticals**.

📂 **[Audit portfolio & findings index →](https://github.com/Tejanadh/audit-portfolio)**  ·  🧠 **[auditooor — my audit methodology →](https://github.com/Tejanadh/auditooor)**

---

## Highlights

- **Dual-ecosystem** — active offensive research on **EVM and Solana** (Rust + Solidity), a combination most auditors don't carry.
- **10+ protocols** publicly researched — Kamino, DEXE, Symbiotic, 1inch-Solana, Jupiter, Ethena, EigenDA, Hyperbridge, Azul, ERC-4337 EntryPoint.
- Findings span **oracles, account abstraction, restaking, governance, data availability, bridges, and gas-accounting.**
- One accounting-desync finding **disclosed via Cantina (#292)**; active in **Immunefi audit competitions** and private coordinated-disclosure programs.
- **Every claim is backed by a runnable PoC** against the real implementation — never a staged log.

---

## 🧠 Expertise

| Skill | Depth |
|-------|-------|
| Solidity / EVM | ⚡⚡⚡ |
| Rust / Solana + Anchor | ⚡⚡⚡ |
| Foundry — invariant + mainnet-fork testing | ⚡⚡⚡ |
| Hardhat / JS & TS tooling | ⚡⚡ |
| C / low-level systems | ⚡⚡ |

**Where I tend to find bugs**

- Oracle staleness, decimal/timestamp mismatches, and liveness asymmetry
- Vault / share-token accounting and rounding-direction drift
- Voting-power and governance guard gaps
- Restaking / slashing accounting desync
- Account-abstraction paymaster & EntryPoint gas-accounting edges
- Access-control and role-boundary violations
- Cross-chain / bridge message-path assumptions
- Unbounded growth, first-depositor / last-withdrawer, and OOG boundary paths

---

## 🎯 Selected findings

> Severity is **research framing**, not a payout decision. Links go to public writeups / PoCs. Work under active embargo is withheld until publication is permitted.

| Protocol | Severity | Finding | What is proven | Link |
|----------|----------|---------|----------------|------|
| **ERC-4337 EntryPoint v0.8** | **Critical** | `postOp` OOG failure charges paymaster for overhead beyond `paymasterPostOpGasLimit` (EIP-4337 §4.3.1), even with empty `postOp` | Foundry PoCs + fix PR | [Repo](https://github.com/Tejanadh/entrypoint-poc) · [Fix PR](https://github.com/Tejanadh/account-abstraction/pull/1) |
| **Kamino / Scope** | **High** | Derived oracles stamp `DatedPrice` with refresh-time `Clock`, not source time — defeats KLend age checks after a permissionless refresh | Public source + live RPC vault-slot lag | [Repo](https://github.com/Tejanadh/kamino-security-research) |
| **DEXE Governance** | **High** | `delegateTokens` missing the `ifNotStaken` guard → stake + delegate double-use of voting power | Source gap + Hardhat repro | [Repo](https://github.com/Tejanadh/dexe-gov-bug-report) |
| **Symbiotic BaseSlasher** | **High** | Slash path ignores `Vault.onSlash` return → phantom cumulative slash / shared-vault desync *(disclosed via Cantina #292)* | Foundry accounting repro | [Repo](https://github.com/Tejanadh/symbiotic-critical-research) |
| **1inch Solana** | **High** *(privileged)* | `rescue_funds_for_order` issues after order close — requires whitelisted resolver | Anchor PoC | [Repo](https://github.com/Tejanadh/1inch-solana-rescue-theft-research) |
| **Jupiter Lend** | **Med–High** *(design)* | Asymmetric oracle max-age: user ops fail at 600s while liquidations continue to 7200s | Program constants + fork scripts | [Repo](https://github.com/Tejanadh/jupiter-lend-oracle-asymmetry) |
| **Ethena Minting V2** | **Latent / Medium** | `verifyNonce` truncates `uint128`→`uint64` — `N` and `N+2^64` collide | Live `verifyNonce` collision | [Repo](https://github.com/Tejanadh/ethena-nonce-truncation-dos) |
| **EigenDA** | **Research** | `confirmBatch` header-trust seam + cert/orbit census | 59+ fork tests; prod paths fail-closed | [Repo](https://github.com/Tejanadh/eigenda-security-research) |
| **Hyperbridge** | **Research** | Decimal-scaling / replay / fee / timeout hypotheses | Offline sims — not claimed as prod criticals | [Repo](https://github.com/Tejanadh/hyperbridge-security-research) |
| **Base L1 — Azul** | **Verified safe** | `AggregateVerifier` multi-proof census | 23 mainnet-fork tests confirm fail-closed — no vuln | [Repo](https://github.com/Tejanadh/azul-multi-proof-analysis) |

> Additional work is under private coordinated disclosure / bounty programs and is not listed until publication is allowed.

---

## 🏅 Recognition & disclosures

- **Symbiotic** — accounting-desync finding **responsibly disclosed via Cantina (#292)**.
- **ERC-4337 EntryPoint** — reproduced an EIP-spec-relevant paymaster overcharge with a **fix PR**, cross-checked against the **Safe 4337 Module**.
- Active in **Immunefi audit competitions** and **private coordinated-disclosure** programs (embargoed findings published once results are public).

---

## 🧭 How I work

- **Adversarial-first.** Every state change is a hypothesis until I've traced who can reach it and what it costs to push past intended bounds.
- **Boundary-obsessed.** Zero-state, first-depositor, last-withdrawer, dust, and out-of-gas paths get more attention than the happy path.
- **Mechanical proof, not vibes.** Findings ship with a deterministic PoC on live RPC / mainnet fork. If I can't make it break in a test, I don't claim it does.
- **Honest severity.** Privilege, reachability, and *current* exploitability are stated up front — I'll down-rate my own finding before I'll inflate it.
- **Negative results count.** A verified fail-closed path is documented, not discarded — ruling a path out is worth as much as breaking one.

---

## ✍️ Writing & methodology

- 🧠 **[auditooor](https://github.com/Tejanadh/auditooor)** — my reward-first audit methodology: target selection, invariant-first hunting, and the EV / impact / novelty / proof gates.
- 📝 **[Firelight competition notes](https://github.com/Tejanadh/firelight-immunefi-notes)** — how I approach a live audit competition (methodology only, findings embargoed).
- 📂 **[audit-portfolio](https://github.com/Tejanadh/audit-portfolio)** — full findings index + the report format I deliver in.

---

## 👤 About

B.Tech Computer Science · ~2 years of independent smart contract security research across Solana and Ethereum.

**Open to:** remote **Smart Contract Security Researcher / Auditor** roles — full-time, part-time, or internship — and independent audit engagements with teams that value reproducible PoCs and honest severity over volume.

**Reach me:** [email](mailto:tejanadh927@gmail.com) · DMs open on [X / @TEJANadh10](https://x.com/TEJANadh10).

<sub>Responsible disclosure first. Public material covers only issues already reported or explicitly safe to publish.</sub>

<sub>`#smart-contract-security` · `#audit` · `#solidity` · `#rust` · `#solana` · `#ethereum` · `#defi` · `#foundry` · `#web3-security`</sub>
