## 🛠️ Homelab Architecture & Constraints

These Docker Compose files are heavily customized to accommodate the specific limitations and quirks of my current environment. If you are referencing or forking these configurations, please keep the following restrictions in mind:

1. **🚫 Network Control Limitations**
   * I do not have access to the main router settings. Therefore, there is **no possibility of port forwarding** or centralized firewall rule management.

2. **📶 Fast Ethernet Bottleneck**
   * The entire lab runs off a Wi-Fi extender's ethernet port, which is limited to **Fast Ethernet (100 Mbps)**. This provides enough bandwidth for my current needs, but it is a known bottleneck that will require an upgrade in the future.

3. **🗄️ UGREEN Docker Quirks**
   * UGREEN systems handle Docker in their own unique way. Any Compose files specifically built or modified for UGREEN environments will be **heavily noted and documented** to reflect these necessary workarounds.

4. **🔄 Dynamic IP Challenges**
   * I currently cannot guarantee a consistent static IP for my UGREEN NAS setups. Containers that require direct NAS access may need periodic manual IP updates to maintain connectivity.

5. **⏱️ Maintenance Philosophy**
   * This is a personal homelab, and my time to actively tinker with it is limited. While updates to this repository may be sparse, the overarching goal is to build a highly replicable, **"set it and forget it"** infrastructure.
