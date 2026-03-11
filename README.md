# Marcus's Debian Home Lab Documentation (WIP)

##  Overview


This documentation captures the configuration, deployment, and tools used in the Debian Home Lab setup.  
The lab includes Docker services, VS Code Remote development, SMB mounts, file management, networking tools, and secure authentication.

## Table of Contents

1. [Overview](#overview)
2. [System Environment](#2-system-environment)
3. [Public/Private Key Authentication for SSH](#3-publicprivate-key-authentication-for-ssh)
4. [Docker & FileBrowser Setup](#4-docker--filebrowser-setup)
5. [SMB / CIFS Mounts](#5-smb--cifs-mounts)
6. [Remote Development & SSH Access](#6-remote-development--ssh-access)
   - [VS Code Remote Server](#61-vs-code-remote-server)
   - [Public/Private Key Authentication](#62-publicprivate-key-authentication-for-debian)
7. [Tailscale VPN](#7-tailscale-vpn)
8. [Enterprise Splunk](#8-Splunk)
10. [Summary of Projects](#10-summary-of-projects)
---

## 2. System Environment

- **Host OS:** Headless Debian Linux based Home server   
- **Remote access:** SSH, VS Code Remote  
- **Key tools installed:**
  - Docker & Docker Compose
  - Git
  - SMB/CIFS client for network mounts
  - FileBrowser for web-based file management
  - Tailscale (VPN)
  - VS Code Server (remote development backend)

---

## 3. Public/Private key authentication for SSH

- Initialized SSH key-based authentication for the Debian server to remove password login.
  
- **Public/Private Key Authentication:**
  - Generated key pair on the local machine:
  - Private key is stored securely on the machine.
  - Public key is copied to the server in Ex. ~/.ssh/authorised_keys.
  - When Logging in via SSH:
  - Your SSH client decrypts it using your private key.
  - If decryption succeeds, login is granted + no password is needed.
 
- Benefits:
  - Improved security: Passwords are never sent over the network.
  - Convenience: Log in without typing a password each time.
  - Automation: Useful for scripts, CI/CD pipelines, and automated deployments.
  - Access control: Easily revoke access by removing a public key from authorised_keys.

---

