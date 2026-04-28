# 🖥️ Homelab Infrastructure & Configurations

Welcome to the documentation and configuration repository for my homelab. This space tracks my Docker setups, virtual machines, networking quirks, and self-hosted services.

> ⚠️ **STATUS: HEAVY WORK IN PROGRESS** > This lab is actively being built, tested, and reconfigured. Expect frequent changes, broken links, and ongoing optimizations as I deploy new services.

---

## ⚙️ Hardware Architecture

My computing environment is split into independent compute nodes and a multi-tiered NAS storage ecosystem. 

### 🧠 Compute Nodes: HP EliteDesk 600 G6 Micro Form Factor
I run **4 separate HP EliteDesk 600 G6 machines**. Rather than a unified compute cluster, these are standalone nodes. While some are grouped together within a Proxmox Datacenter for easier management, at least one is dedicated to running Windows Server directly. Each machine shares a similar baseline:
* **CPU:** Intel Core i5-10500T (per node)
* **RAM:** 64GB DDR4 (per node)
* **Storage:** 1x 1TB NVMe & 1x 512GB NVMe (per node)
* **Networking Breakdown:**
  * **Nodes 1-3:** 10GbE + 1GbE (vPro)
  * **Node 4:** 2.5GbE + 1GbE (vPro)

### 🗄️ Storage & Backups: UGREEN NAS Ecosystem
Data is handled by a tiered approach using UGREEN systems, allowing for redundancy, scratch space, and disaster recovery:
* **Primary Storage:** UGREEN NAS DXP6800 Plus (6-bay)
* **Secondary Storage:** UGREEN NAS DXP4800 Plus (4-bay)
* **Disaster Recovery:** UGREEN NAS DXP2800 (2-bay) — *Located Offsite for backups*

---

## 💻 Software Stack

The foundational software running across these independent machines includes:
* **Proxmox VE:** The primary hypervisor managing the majority of my nodes, grouped into a Proxmox Datacenter.
* **Windows Server 2025:** Running natively on one of the EliteDesks to handle specific enterprise-level and domain services.
* **Docker:** The backbone of most of my self-hosted services, distributed across the environment.
* **Virtual Machines:** Dedicated VMs for specific, isolated workloads.

---

## 🚧 Homelab Architecture & Constraints

These configurations and Docker Compose files are heavily customized to accommodate the specific limitations and quirks of my current environment. If you are referencing or forking these files, please keep the following restrictions in mind:

1. **🚫 Network Control Limitations**
   * I do not have access to the main router settings. Therefore, there is **no possibility of port forwarding** or centralized firewall rule management. Everything must be handled internally.

2. **📶 Fast Ethernet Bottleneck**
   * The entire lab currently runs off a Wi-Fi extender's ethernet port, which is limited to **Fast Ethernet (100 Mbps)**. This provides enough bandwidth for my current needs, but it is a known bottleneck that will require an infrastructure upgrade in the future.

3. **🐳 UGREEN Docker Quirks**
   * UGREEN systems handle Docker in their own unique way. Any Compose files specifically built or modified for UGREEN environments will be **heavily noted and documented** to reflect these necessary workarounds.

4. **🔄 Dynamic IP Challenges**
   * I currently cannot guarantee a consistent static IP for my UGREEN NAS setups. Containers that require direct NAS access may need periodic manual IP updates to maintain connectivity.

5. **⏱️ Maintenance Philosophy**
   * This is a personal homelab, and my time to actively tinker with it is limited. While updates to this repository may be sparse at times, the overarching goal of this project is to build a highly replicable, resilient, **"set it and forget it"** infrastructure.
