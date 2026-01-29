# 📡 AI-Fi :: Command Center (CNS - Central Nervous System)

## 🌌 The Nexus
The Command Center is the high-security orchestration hub of the AI-Fi Organism. It governs the internal network topology and manages the cryptographic identities required for cluster coherence.

## 🗺️ Cluster Architecture Diagram
```mermaid
graph TD
    CC[Command Center] -->|SSH/Key| SAPI[Server API]
    CC -->|SSH/Pass| MP[Maverick Pro]
    CC -->|SSH/Pass| SE[Strategy Engine]
    CC -->|SSH/Key| WW[Autonomous Workers]
    CC -->|SSH/Key| PL[Persistence Layer]
    CC -->|SSH/Pass| WC[Web Client]
    CC -->|SSH/PEM| AWS[AWS GPU Node]
    
    MP -->|Signals| SE
    AWS -->|Inference| SE
    SE -->|Execution| WW
    WW -->|Logs| PL
    PL -->|State| SAPI
    SAPI -->|JSON| WC
```

## 🧠 Operational Manifest
- **`ShadowPortfolioEngine.cjs`**: The real-time valuation engine. Uses an Atomic Load Pattern for state persistence.
- **`scan_cluster.py`**: A multi-threaded prober using `pexpect` to verify system integrity across 8 nodes.
- **`v10_audit_method.js`**: The canonical method for auditing system 'stress' levels.

## 🛠️ Failure Modes & Mitigations
| Failure | Mitigation |
| :--- | :--- |
| **Key Corruption** | Restore from GitHub Secret or `RECONSTRUCTION.md`. |
| **IP Drift** | Update `NODES` array in `scan_cluster.py` and `CLUSTER_ACCESS.md`. |
| **Sync Lag** | Adjust cron frequency in `sync_shadow_to_web.sh`. |

---
[Master Construction Blueprint](https://github.com/kunleulysses/aifi-command-center/blob/master/RECONSTRUCTION.md)
