# Banncoin Tech Truth Sheet (public)

**Chain ID:** `banncoin-mainnet-1`  
**Consensus:** PoW (leading-zero SHA-256 over canonical header JSON)  
**Target:** dynamic clamp 5↔6 (occasionally higher right after very fast blocks)  
**Block Reward:** **458 BNC** (coinbase to the submitted `wallet`)  
**Finality:** 1 block (practical, single-node era)

## RPC (JSON per line over TCP: `104.248.10.130:17536`)
- `get_status` → `{height, current_hash, genesis_hash, mempool, …}`
- `get_mining_job` → `{height, prev_hash, merkle_root, timestamp, target_prefix}`
- `submit_block` → `{type:'block_accepted', height, hash}` on success

## Explorer
- Tip: `https://banncoin.org/live/explorer`
- Per-address totals: `https://banncoin.org/live/explorer?addr=bnc1…`

## Files on node
- Blocks: `/root/bnc_chain/blockNNNNNNNNN.json`

## Known gaps (actively planning)
- Signed transactions (account+nonce+sig) + balances/replay
- Simple self-custody wallet (passkeys / social recovery)
- Multi-node / deterministic finality path
- Audit + devnet/testnet

We’re shipping docs first; no protocol changes implied by this sheet.
