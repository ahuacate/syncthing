# Syncthing Build
This recipe is for setting up Syncthing.

Network Prerequisites are:
- [x] Layer 2 Network Switches
- [x] Network Gateway is `192.168.1.5`
- [x] Network DNS server is `192.168.1.5` (Note: your Gateway hardware should enable you to a configure DNS server(s), like a UniFi USG Gateway, so set the following: primary DNS `192.168.1.254` which will be your PiHole server IP address; and, secondary DNS `1.1.1.1` which is a backup Cloudfare DNS server in the event your PiHole server 192.168.1.254 fails or os down)
- [x] Network DHCP server is `192.168.1.5`

Other Prerequisites are:
- [x] Synology NAS, or linux variant of a NAS, is fully configured as per [SYNOBUILD](https://github.com/ahuacate/synobuild#synobuild).
- [x] Proxmox node fully configured as per [PROXMOX-NODE BUILDING](https://github.com/ahuacate/proxmox-node/blob/master/README.md#proxmox-node-building).
- [x] Syncthing LXC with Syncthing SW installed as per [SyncthingLXC - Ubuntu 18.04](https://github.com/ahuacate/proxmox-lxc-homelab/blob/master/README.md#400-syncthing---ubuntu-1804).

Tasks to be performed are:
- [ ] 1.00 Setup LazyLibrarian settings
- [ ] 1.01 Setup LazyLibrarian interface settings
- [ ] 1.02 Setup LazyLibrarian importing settings
- [ ] 1.03 Setup LazyLibrarian downloader settings
- [ ] 1.04 Setup LazyLibrarian providers settings
- [ ] 1.05 Setup LazyLibrarian processing settings
- [ ] 1.06 Setup LazyLibrarian categories settings
- [ ] 2.00 Create Lazylibrarian backup
- [ ] 3.00 Restore Lazylibrarian backup
- [ ] 00.00 Patches & Fixes

## 1.00 Setup Syncthing settings
In your web browser type `https://192.168.80.122:8384` and click `Actions` > `Settings`.

### 1.01 Setup Syncthing General settings
Give your Proxmox Syncthing client device a name so its easily identifiable (syncthing-identifier). Something like `syncthing-berlin` or whatever naming concention you choose.

![alt text](https://raw.githubusercontent.com/ahuacate/lazylibrarian/master/images/interface.png)
