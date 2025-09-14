# Banncoin Privacy v0 (draft)

**Goal:** private-by-default *option*, with selective disclosure. Keep it simple first:
- Stealth-style receive (one-time addresses derived from pubkey)
- Encrypted memos
- Optional view keys
- Selective proofs for “I paid X → Y amount Z” without full reveal

## v0 plan
- `memo`: base64 ciphertext (ECIES over recipient pubkey)
- `to`: `bnc1…` (normal), optionally `bnc1+stealth:…` later
- Explorer: show “private transfer” badge when memo is encrypted

## Later
- Full note commitments / nullifiers
- ZK proofs for amount + sender/receiver privacy
- Per-tx “reveal” proof (selective disclosure)

# Banncoin Privacy v0 (draft)

**Intent:** give ordinary users practical privacy from day one, while preserving lawful auditability *by choice*. Start simple; evolve to stronger cryptography without breaking UX.

## v0 goals
- Obfuscate recipient in day-to-day flows (stealth address pattern)
- Encrypted memos (small note per transfer)
- View key (optional, user-shared) to reveal history to a counterparty or auditor
- No global blacklists; no chain-wide “freeze” affordance

## Components

### 1) Stealth addressing (simple)
- Each account has a **public address** (`bnc1...`) and a **scan/view key**.
- Sender derives a one-time “stealth receiving address” from recipient’s public key + ephemeral.
- Chain only sees the one-time address; recipient scans to claim.

### 2) Encrypted memo
- Up to 128 bytes encrypted with recipient’s pubkey.
- Used for invoices, order IDs, or human context.

### 3) View keys (selective disclosure)
- A user can share a **read-only view key** with a person/app to show their historical inflows/outflows.
- No spending rights. Revocable by rotating account keys.

### 4) Forward path (not in v0)
- v1: stronger receiver privacy (dual-key stealth)
- v2: shielded amounts via ZK (range proofs)
- v3: fully-private pool (ZK transfers), with **user-triggered** reveal proofs

## Threats not solved in v0
- Amounts are visible (until ZK-range phase).
- Global network-level correlation (mitigated later with encrypted mempool + batching).
- Sophisticated chain analysis (reduced over time with fair-order + Tide encryption).

**Summary:** v0 gets us “private-enough-for-normal-people” without breaking simplicity. Evolve to ZK as adoption grows.
