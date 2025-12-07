# Remnawave Installer

A comprehensive Bash script for installing and managing the **Remnawave Reverse Proxy** ecosystem (Panel and Node). This tool simplifies the deployment of a secure reverse proxy infrastructure using Docker, Nginx, and Xray/Sing-box.

## 🚀 Quick Start

Run the installer directly with a single command:

```bash
bash <(curl -Ls https://raw.githubusercontent.com/snaplyze/remnawave-installer/refs/heads/main/remnawave_installer.sh)
```

## ✨ Features

*   **Automated Installation:** seamlessly installs Docker, Nginx, and Certbot.
*   **Flexible Deployment:** Supports installing Panel + Node, Panel only, or Node only.
*   **Certificate Management:**
    *   Automatic SSL generation via Let's Encrypt.
    *   Support for Cloudflare API (wildcard certs) and HTTP-01 challenges.
*   **Security:**
    *   Panel port (8443) management (open/close access).
    *   "Selfsteal" domain configuration for anti-probing.
    *   Random web template installation for camouflage.
*   **Customization:**
    *   **Custom Config Names:** Set your own names for configuration profiles, nodes, and hosts during installation (default: "StealConfig").
    *   **Extensions:** Integration with third-party tools like WARP Native and Backup/Restore utilities.
    *   **IPv6:** Easy toggle for IPv6 support.
*   **Maintenance:**
    *   Built-in update mechanism for the script (`update_remnawave_reverse`).
    *   Container management (Start, Stop, Restart, Logs).
    *   Easy uninstall options.

## 📋 Requirements

*   **OS:** Debian 11/12 or Ubuntu 22.04/24.04.
*   **Permissions:** Root access is required.
*   **Network:** Ports 80 and 443 must be available.

## 🛠 Usage

After running the script, you will be presented with an interactive menu:

1.  **Install Remnawave Components:** Main installation options.
2.  **Reinstall:** Clean reinstall of panel or node.
3.  **Manage Panel/Node:** Control services and view logs.
4.  **Extensions:** Install extra features like WARP.
5.  **Manage Certificates:** Renew or generate new SSL certificates.
