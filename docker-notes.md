My docker compose files will be customized to match the following restrictions in my homelab:
  1.) I do not have access to router settings, so there will be no possility of port forwarding or firewall rule management
  2.) Everything is running off a wifi extender's ethernet port, and that ethernet port is only FAST ETHERNET at 100mbps (good enough for me, will need to upgrade in the future)
  3.) UGREEN has its own quirks with docker, so UGREEN docker compose files will be noted HEAVILY as such
  4.) I'm unsure if I'm going to have a static IP consistently for my UGREEN NAS systems, so containers needing NAS access might have to be constantly updated with IP's to make sense
  5.) This is my homelab that I don't have much time to work on. Updates will be sparce, but my goal is to create a replicatable "set it and forget it" setup. 
