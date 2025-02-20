![Runix-Cloud](https://github.com/user-attachments/assets/f8b0bb9e-64af-4501-bfd8-77bf6109c81f)


# Runix Cloud server Setups

## Overview
Runix.cloud is a personal homelab server running in my UBC dorm in collaboration with ![Hamzah Chaudhry](https://github.com/hamzahchaudhry), designed for hosting web services, virtual machines, personal cloud backups, and various experiments. This repository contains the configuration files and automation scripts used to manage and deploy my homelab setup efficiently.

## Server Specifications (Matsya for now)
- **Model:** Lenovo System x3250 M6
- **Processor:** Intel Xeon E3-1220v6
- **Memory:** 32GB ECC DDR4 RAM
- **Storage:** 256GB SSD (OS) + 4x 3.5" hot-swap bays (future expansion)
- **Networking:** Dual 1GbE NIC + Dual SFP+ 10GbE NIC
- **Management:** IPMI for remote monitoring and management
- **Operating System:** Proxmox VE (running multiple VMs & containers)

## Use Cases
- **Web Hosting** - Running Nginx-based web servers.
- **Virtual Machines & Containers** - Managing various services using Proxmox.
- **SSH Access** - Secure remote access for development and administration.
- **Networking Experiments** - Testing VPNs, routing, and firewall rules.
- **File Storage & Backup** - Hosting personal and project-related files.
- **Self-Hosting Services** - Running various self-hosted applications.

## Network & Accessibility
The server is currently **not publicly accessible** for security reasons. Instead, I use **Tailscale VPN** to securely connect to it from anywhere. Friends and family can request access to specific services by contacting me and will get certain access when publicly available.

### **Future Plans for Public Access**
Eventually, the server will be accessible via **runix.cloud** or **matsya.runix.cloud**. For now, only one main server is accessible, but in the future, specific services will be reachable through subdomains.

## Repository Contents
This repository includes:
- **Proxmox configurations** (`/etc/pve`, `/etc/qemu-server`, `/etc/lxc`)
- **Network settings** (`/etc/network/interfaces`, firewall rules, DNS settings)
- **NGINX configuration** (reverse proxy, web hosting setup)
- **System automation scripts** (cron jobs, systemd services)
- **Backup configurations** (Proxmox `vzdump` settings, storage mappings)

## Deployment
To replicate or restore this setup on another machine:
```sh
# Clone the repository
git clone https://github.com/yourusername/matsya-setup.git ~/runix.cloud/matsya-setup

# Copy configuration files (ensure backups first)
rsync -av ~/runix.cloud/matsya-setup/ /etc/

# Restart services to apply changes
systemctl restart networking nginx pveproxy
```
(Note: Ensure sensitive files like `/etc/shadow` and private keys are excluded.)

## Contact & Contributions
If you're interested in collaborating on this homelab setup or add more, feel free to reach out!

---
🚀 *Matsya is an evolving project—stay tuned for more updates!*
![IMG_3813-fotor-2025021831821](https://github.com/user-attachments/assets/12df5ef3-86a3-441d-b7ba-d39c8bb5cd08)


