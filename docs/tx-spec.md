# Banncoin TX Spec (v0 draft)

**Goal:** enable real payments with account/nonce model, simple fees, and replay → balances.

## 1. State & Keys
- **Account:** `{ address, balance, nonce }`
- **Address:** current `bnc1…` form; maps to an ed25519 public key (v0).
- **Nonce:** starts at `0`; must equal the next expected value when a tx is accepted.

## 2. Transaction (JSON, canonical)
```json
{
  "type": "tx",
  "from": "bnc1…",
  "to": "bnc1…",
  "amount": 12345,
  "fee": 100,
  "nonce": 7,
  "memo": "optional string",
  "pubkey": "base64-ed25519",
  "sig": "base64-ed25519"
}
