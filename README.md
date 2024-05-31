# homelab
## Welcome to my home lab set-up

### Hardware
#### Work Station
My main workstation is a custom rig that I built at the end of 2012. Props to NewEgg for a basically eternal order history. I've upgraded the GPU, updated Windows, and added an extra HD, but it's largly the same as it was when it was built and it's still going strong. 

#### Virtualization Server
I picked up a refurbished HP EliteDesk and bumped up the RAM and added a 2 port NIC. I had originally used this as a bare metal pfSense firewall- which worked great. But after upgrading to a Ubiquity UDM Pro, I repurposed it for Proxmox. 
#### Misc
Random laptops, phones, tablets, etc etc

### Services
- Proxmox
- Home Assistant
- Portainer
- Uptime Kuma
- Nginx Proxy Manager
- Authentik
- Heimdal
- WikiDocks
- BitWarden
- Wazuh
- Ollama

Wazuh, Utk, and HA are running on containers/ VM directly on Proxmox. Pretty much everything else is dockerized and using Protainer for managment.

### Networking
I've migrated from pfSense to Ubiquity. No complaints about pfSense, but I wanted something a little more professional and frankly the administration is easier. Also the blinky lights and the screen are great. I'm running a few VLANs to help keep services segregated. There are separate VLANs for anything Google so that I can keep an 👁️ on them. Another VLAN for 'dirty' devices like cell phones. Using NPM and Cloudflare I'm able to proxy all my internal connections and use a wildcard SSL certificate to make sure I'm using HTTPS wherever possible. I use Cloudflare tunnels for anything I might want to expose. 

### Security
I try to adhere to most standard security practices. Keeping least privileges in mind. I've elected to not keep password storage on prem. So far BitWarden has proven reliable. And if, heaven forbid, something happens, I really don't have to worry about recovery. The Ubiquity firewall is great. They offer great tools for monitoring network traffic, have built in ad blockers and a lot of other tools. And it's just so much easier to work with. I use Wazuh as a SIEM for the home-lab. It's really easy to get the agents installed. There's not much action but it is good to have a picture of the device vulnerabilities in the network. I've started using Authentic for SSO. It's still new, but so far it's great. There is definitely a learning curve, but it is work it to not need a dozen different passwords on a given day. 

### Backup
Not quite up to a 3-2-1 scheme. For my purposes it's not all that critical. I _do_ backup all my services and I keep a synced copy of weekly backups in an encrypted S3 bucket. 

