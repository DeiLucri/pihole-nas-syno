# Docker-compose file for creating a pihole container on a synology nas with macvlan network 
## SSH
1. Create the folders needed for pihole, generally on Syno NAS, the docker directory is /volume1/docker/
```bash
cd /volume1/docker && mkdir -p pihole/{pihole,dnsmasq.d}
```
2. Download docker-compose.yml to /volume1/docker/pihole
```bash
cd /volume1/docker/pihole && curl -o docker-compose.yml https://raw.githubusercontent.com/DeiLucri/pihole-nas-syno/main/docker-compose.yml
```
3.  Modify the file to change the macvlan network and container ip address
4.  Create the container 
```bash
sudo docker-compose up -d
```
5. Connect via IP and port set on web browser

## Notes :
- On the synology nas server, do not modify the DNS server and indicate the Pihole container. *By default, the Pi-hole container is isolated from the host network, which means it cannot communicate directly with the NAS. This is a security feature of macvlan networks**

