
---

# 📄 rpc-policy.md (paste this)
```markdown
# Banncoin RPC Policy (beta)

- **Port:** `17536/tcp` (public, rate-limited via UFW `limit`)
- **Methods exposed:** `get_status`, `get_mining_job`, `submit_block`
- **Not exposed:** transactions, admin, debug, or state-changing calls
- **Fair use:** 1–2 long-lived connections per IP; abusive behavior may be throttled/blocked
- **Security:** endpoint behind UFW with per-IP rate-limit; logs monitored
- **Contact:** open an issue in the docs repo or DM a maintainer with timestamp/IP if you hit problems
