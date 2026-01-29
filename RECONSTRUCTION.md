# 🏗️ AI-Fi CLUSTER RECONSTRUCTION GUIDE

This guide explains how to reassemble the AI-Fi nodebase from the GitHub backups.

## 📦 Repositories

| Node | GitHub Repository |
| :--- | :--- |
| **Command Center** | [aifi-command-center](https://github.com/kunleulysses/aifi-command-center) |
| **Maverick Pro** | [aifi-maverick-pro](https://github.com/kunleulysses/aifi-maverick-pro) |
| **Strategy Engine** | [aifi-strategy-engine](https://github.com/kunleulysses/aifi-strategy-engine) |
| **Web Client** | [aifi-web-client](https://github.com/kunleulysses/aifi-web-client) |
| **Server API** | [aifi-server-api](https://github.com/kunleulysses/aifi-server-api) |
| **Auto Workers** | [aifi-auto-workers](https://github.com/kunleulysses/aifi-auto-workers) |
| **Persistence** | [aifi-persistence-layer](https://github.com/kunleulysses/aifi-persistence-layer) |
| **AWS GPU Node** | [aifi-aws-gpu-node](https://github.com/kunleulysses/aifi-aws-gpu-node) |

---

## 🚀 Restoration Steps

### 1. Provision New Infrastructure
- Create 7 Vultr instances (Ubuntu).
- Create 1 AWS GPU instance (Ubuntu).
- Ensure they are in a private network or update the IP addresses in the configuration files.

### 2. Set Up Command Center
- Clone the `aifi-command-center` repo to the new Command Center node.
- Re-generate or restore the SSH keys (`id_rsa`) and distribute them to the internal nodes.
- Update `/root/CLUSTER_ACCESS.md` with the new IP addresses.

### 3. Deploy Internal Nodes
For each internal node (Maverick, Strategy, Web, API, Workers, Persist):
1. SSH into the node.
2. Clone its corresponding repository.
3. Install dependencies: `npm install`.
4. Run setup scripts if available (e.g., `setup-db-node.sh` on Persistence).

### 4. Persistence Layer (Database)
- Restore the database from the `aifi_dump.sql` file in the `aifi-persistence-layer` repo.
- Command: `mysql -u [user] -p [db_name] < aifi_dump.sql`

### 5. Web Client
- The `aifi-web-client` contains the frontend. Ensure `npm run dev` or equivalent is started.
- Verify that API endpoints in the frontend code reflect the new Server API IP.

### 6. Verify Connectivity
- Use the `verify_all.py` script on the Command Center to test connections between all nodes.

---

## ⚡ Critical Files to Check
- `CLUSTER_ACCESS.md`: The map of the whole system.
- `id_rsa`: The skeleton key for internal node access.
- `.env` files: Check for any API keys or secrets that might not have been in the repo.

> [!IMPORTANT]
> This backup excludes `node_modules` and log files to stay lightweight. Always run `npm install` after cloning a repo.
