# Banncoin — 90-Day Plan (TX · Wallet · Security)

**Scope:** deliver real payments (signed tx), a minimal wallet flow, and basic hardening—without breaking mining.

---

## Weeks 0–2 (Specs & scaffolding)
**TX**
- Spec: account model (balances, nonces), ed25519 signatures, canonical tx JSON
- Mempool rules: size caps, basic validity, anti-spam

**Wallet**
- UX sketch: QR send/receive, passkey or “Kin-keys” social recovery concept
- Sponsor-gas pattern (Patron): allow zero-balance tx in pilot

**Security/Ops**
- Devnet config; journalctl filters; simple health endpoint; backup runbook in docs

---

## Weeks 2–4 (Prototype & devnet)
**TX**
- Implement tx verify + apply; chain replay to compute balances
- Devnet: submit_tx RPC (devnet only)

**Wallet**
- CLI or minimal web demo: create address, show balance (from replay), sign & send to devnet

**Security/Ops**
- UFW profiles (public/mining vs invite-only); log rotation; basic rate counters

---

## Weeks 4–8 (Testnet & explorer)
**TX**
- Testnet: open submit_tx; mempool tuning; inclusion policy draft (“Right-of-Passage” window)

**Wallet**
- Minimal desktop/web wallet for testnet: passkey login, QR send, human-readable intent preview

**Security/Ops**
- Threat model v1; simple alerting; per-IP caps on submit_tx at the edge

---

## Weeks 8–12 (Pilot mainnet payments)
**TX**
- Mainnet: enable submit_tx for a small allowlist (creators/merchants pilot)
- Explorer: show recent payments + per-address balance via replay

**Wallet**
- “Tip Banncoin” flow for creators; sponsor-gas for first N tips

**Security/Ops**
- Pre-audit checklist; log scrubs; backup/restore drill; document rollback plan

**Success criteria**
- End-to-end tip/merchant payment on mainnet with replayed balances
- 3–5 external miners and 3–5 creators actively using it
