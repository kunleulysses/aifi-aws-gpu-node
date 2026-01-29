# 📡 AI-Fi :: Command Center

The central orchestration hub for the AI-Fi cluster.

## 🛠️ Role
- Managing SSH access via `id_rsa`.
- Hosting `CLUSTER_ACCESS.md` (The master IP map).
- Running cross-node orchestration scripts.
- Verifying cluster health (`verify_all.py`).

## 🚀 Restoration Instructions
1. **Provision**: Create a fresh Vultr/Ubuntu instance.
2. **Setup**: Clone this repo to `/root`.
3. **Keys**: Restore `id_rsa` to `/root/.gemini/antigravity/scratch/id_rsa` and set permissions (`chmod 600`).
4. **Networking**: Update `CLUSTER_ACCESS.md` with current cluster IPs.
5. **Verify**: Run `python3 verify_all.py` to ensure you can reach all nodes.

---
[Back to Master Reconstruction Guide](https://github.com/kunleulysses/aifi-command-center/blob/master/RECONSTRUCTION.md)
