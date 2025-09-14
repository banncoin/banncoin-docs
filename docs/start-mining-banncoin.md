# Start Mining Banncoin (BNC)

CPU-friendly. No premine. **Rewards per seal: 458 BNC**.

**Public RPC (beta):** `104.248.10.130:17536`  
The endpoint is open with a light rate-limit. Please mine responsibly.

---

## 1) Download the tools (Windows & Linux)

- Miner (Python): `https://banncoin.org/downloads/banncoin_miner.py`
- Windows helper (optional): `https://banncoin.org/downloads/run_miner.bat`
- Linux helper (optional): `https://banncoin.org/downloads/run_miner.sh`
- SHA256s: `https://banncoin.org/downloads/banncoin_miner.py.sha256.txt`

## 2) Pick a wallet address

Use **your own** BNC address (starts with `bnc1`) to receive rewards.  
(For testing you may temporarily use one of the maintainer addresses below.)

- `bnc1q42uqrkcd7mgduu6klugqg7wrjpxnu93ahgjt7r`
- `bnc1qf499s7rg246g6qdlszjp3wq4aah8fpyqyhjtt0`

## 3) Run the miner

**Windows (PowerShell):**
```powershell
cd $env:USERPROFILE\Downloads\banncoin_site\downloads
python .\banncoin_miner.py --node 104.248.10.130:17536 --wallet "<YOUR_BNC_ADDRESS>"
