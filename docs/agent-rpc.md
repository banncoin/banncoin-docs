# Agent RPC (v0 draft)

**Goal:** let human wallets *and* AI agents interact safely.

## Read endpoints (no auth)
- `/live/explorer` -> { tip_height, hash, timestamp }
- `/addr?bnc1…`    -> { blocks, balance, last[] }  (already proxied via /live/explorer?addr=)

## Write endpoints (future)
- `submit_tx` -> { ok, reason? }
- `quote_tip` -> { est_reward, est_target, fee_hint }

## JSON example (address totals)
GET `/live/explorer?addr=bnc1…`
```json
{"status":"OK","addr":"bnc1…","blocks":123,"balance":56274,"last":[…]}
```
