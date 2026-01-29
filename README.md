# 📡 AI-Fi :: Command Center (The Central Nervous System)

## 🌌 Overview
The **Command Center** is the orchestration heart of the AI-Fi cluster. It handles the secure tunneling, authentication, and state verification across the entire 8-node distributed network.

## 🧠 Role & Responsibility
- **Master Key Management**: Stores and manages the `id_rsa` key used to access internal Vultr nodes.
- **Cluster Mapping**: Maintains `CLUSTER_ACCESS.md`, the source of truth for all internal and external IPs.
- **Orchestration**: Runs scripts that synchronize state and verify the health of the 'Organism'.
- **Deployment Hub**: The origin point for all cluster-wide updates and scp distributions.

## 📂 File Manifest
- `CLUSTER_ACCESS.md`: The master IP/Auth table for the entire cluster.
- `RECONSTRUCTION.md`: The emergency guide for cluster-wide re-provisioning.
- `verify_all.py`: Python verification suite to ensure inter-node connectivity.
- `scan_cluster.py`: Probing tool for identifying active services across the network.
- `services/`: Logic for high-level cluster orchestration.
- `utils/`: Helper functions for network and file operations.

## 🚀 Restoration Deep Dive
1. **Infrastructure**: Provision a Standard Vultr Instance (Ubuntu 22.04).
2. **Environment**: Install `rsync`, `sshpass`, and `git`.
3. **Secrets Restoration**:
    - Restore `/root/.gemini/antigravity/scratch/id_rsa` (Essential for Internal Access).
    - Restore `/root/Touch a girl.pem` (Essential for AWS Access).
    - `chmod 600` both keys immediately.
4. **Verification**: Run `python3 verify_all.py`. If any node is 'Down', check the IP in `CLUSTER_ACCESS.md`.

---
[Master Cluster Guide](https://github.com/kunleulysses/aifi-command-center/blob/master/RECONSTRUCTION.md)
