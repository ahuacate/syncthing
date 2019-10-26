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
- [ ] 1.00 Setup Syncthing settings
- [ ] 1.01 Setup Syncthing General settings
- [ ] 1.02 Setup Syncthing Username & Password GUI Acesss
- [ ] 2.00 Setup Syncthing Proxmox Folder Shares
- [ ] 1.04 Setup LazyLibrarian providers settings
- [ ] 1.05 Setup LazyLibrarian processing settings
- [ ] 1.06 Setup LazyLibrarian categories settings
- [ ] 2.00 Create Lazylibrarian backup
- [ ] 3.00 Restore Lazylibrarian backup
- [ ] 00.00 Patches & Fixes

## 1.00 Setup Syncthing settings
In your web browser type `https://192.168.80.122:8384` and click `Actions` > `Settings`.

### 1.01 Setup Syncthing General settings
Under the `General Tab` give your Proxmox Syncthing device a name which is easily identifiable by you (syncthing-identifier). Something like `syncthing-berlin` or whatever naming concention you choose.

![alt text](https://raw.githubusercontent.com/ahuacate/syncthing/master/images/syncthing-general.png)

### 1.02 Setup Syncthing User Password
Under the `GUI Tab` create a new Proxmox Syncthing username with a strong complex password and record it (i.e oTL&9qe/9Y&RV).

![alt text](https://raw.githubusercontent.com/ahuacate/syncthing/master/images/syncthing-gui.png)

## 2.00 Syncthing Folder Types
Syncthing is prebuilt with the Default Folder only. You many add more folders to share. There are three configurable folder types in Syncthing.
1  Send & Receive Folder
2  Send Only Folder
3  Receive Only Folder

### 2.01 Syncthing Default Folder - Send & Receive
Your Default Folder set to `send & receive` data. Under this setting, a folder will both send changes to and receive changes from remote devices. If you followed our Syncthing installation [guide](https://github.com/ahuacate/proxmox-lxc-homelab/blob/master/README.md#400-syncthing---ubuntu-1804) your default folder location is on your NAS `\\192.168.1.10\cloudstorage\syncthing\Sync`. 

The Default Folder is the location where remote devices sync data to. It works by accepting folders from a given device and storing it in default path/folder id, and for every device that has auto-accept enabled has the same folder shared with you, it gets shared back automatically.

To edit the Default Folder settings  go to your web browser type `https://192.168.80.122:8384` and click `Default Folder` > `Edit` and the `Edit Folder` will appear. Click on `File Versioning` and set as follows:

| Edit Folder | Value
| :---  | :--- 
| **File Versioning**
| File Versioning | `Trash Can File Versioning`
| Clean out after | `30` days

![alt text](https://raw.githubusercontent.com/ahuacate/syncthing/master/images/syncthing-default-editfolder1.png)




