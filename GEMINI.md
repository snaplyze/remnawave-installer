# Remnawave Installer

This directory contains the `remnawave_installer.sh` script, a comprehensive CLI tool for deploying and managing the **Remnawave Reverse Proxy** ecosystem (Panel and Node).

## 📋 Project Overview

The installer automates the setup of a secure reverse proxy infrastructure using Docker. It supports multiple deployment modes (Single Server, Distributed) and includes utilities for certificate management, system optimization, and extensions.

*   **Primary Script:** `remnawave_installer.sh`
*   **Target OS:** Debian 11/12, Ubuntu 22.04/24.04
*   **Core Technology:** Docker Compose, Nginx, Xray/Sing-box (inferred from context), Certbot.

## 🚀 Usage

The script must be run as `root`.

```bash
chmod +x remnawave_installer.sh
./remnawave_installer.sh
```

### Installation Modes
1.  **Panel + Node:** Installs both components on the same server.
2.  **Panel Only:** Installs only the management panel.
3.  **Node Only:** Installs a node and connects it to an existing remote panel.
4.  **Add Node:** Helper to generate credentials for adding a new node to the current panel.

## 🛠 Key Features & Menus

The script presents an interactive menu with the following capabilities:

*   **Install Remnawave Components:** Core installation logic.
*   **Manage Panel/Node:** Start/Stop/Restart containers, view logs, and access the internal CLI (`remnawave_cli`).
*   **Certificate Management:**
    *   Generates SSL certificates via Let's Encrypt.
    *   Supports **Cloudflare API** (for wildcards) and **HTTP-01** challenge methods.
*   **Extensions:**
    *   **WARP Native:** Installs Cloudflare WARP and integrates it into the node's outbound configuration.
    *   **Backup/Restore:** Utilities for data preservation.
*   **System Configuration:**
    *   **IPv6:** Toggle IPv6 support.
    *   **Camouflage:** Installs random web templates for "selfsteal" (anti-probing) domains.

## 📂 Technical Details

*   **Installation Directory:** `/opt/remnawave` (contains `docker-compose.yml` and configs).
*   **Logs:**
    *   Script logs: `/usr/local/remnawave_reverse/remnawave_reverse.log`
    *   Container logs: Accessed via "Manage Panel/Node" > "View logs".
*   **Configuration:**
    *   Nginx configs are modified dynamically to secure the panel port (8443).
    *   `token.txt` is used to store API tokens for local operations.

## ⚠️ Important Considerations

*   **Port 8443:** The panel uses port 8443. The script provides options to open/close this port publicly or restrict it.
*   **Docker:** The script manages the Docker installation. Ensure no conflicting web servers (like standard Nginx/Apache) are binding to port 80/443 before running.
*   **Updates:** The script has a self-update mechanism (`update_remnawave_reverse`).
