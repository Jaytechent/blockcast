# Blockcast Network
Blockcast is DePIN platform focused in content delivery, you  earn by conteibuting your idle internet bandwidth and its  powered by solana.

### Reward Details:

A 6-month Proof of Resources Epoch, rewarding nodes based on their node capacity.

* Top-performing nodes will receive special NFTs at the end of the epoch.

- **Reward rate is based on:**
  - Connection quality (your uplink speed)
  - Reliability (consistent uptime)
  - Hardware score (RAM, disk, CPU)
  - Location (where your IP is physically based)
  - BONUS: Multicast-enabled IPs earn extra points!
- Possible to run with a minimal hardware.
 
---
 
## Enviorement
**Windows Users**:
* Must install Ubuntu on Windows using this [guide](https://github.com/0xmoei/Install-Linux-on-Windows), then continue further steps.

**VPS Users**:
* Get started with a VPS Server! https://vpsdime.com/a/4006/linux-vps
---

## Install Dependecies:
Update packages:
```bash
sudo apt-get update && sudo apt-get upgrade -y
```
Install Packages:
```bash
sudo apt install curl iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev  -y
```
Install Docker:
```bash
sudo apt update -y && sudo apt upgrade -y
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done

sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update -y && sudo apt upgrade -y

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

# Test Docker
sudo docker run hello-world

sudo systemctl enable docker
sudo systemctl restart docker
```

---

## Register Dashboard:
## Register Dashboard:
To get started, [click here to register](https://app.blockcast.network?referral-code=wcXRfc).


---

## Install
```bash
git clone https://github.com/jaytechent/blockcast
```
```bash
cd blockcast
```

---

## Run
```bash
docker compose up -d
```
* Note:If you are running aztec node on same vps, open configuration file with `nano docker-compose.yml` and change the port to `8081` by replacing `8080:8080` with `8081:8080` cos aztec uses the 8080 port.

---

## Check Logs
List Containers:
```bash
docker compose ps
```
Response:
```
NAME                                 IMAGE                             COMMAND                  SERVICE          
beacon-docker-compose-watchtower-1   containrrr/watchtower             "/watchtower"            watchtower
beacond                              blockcast/cdn_gateway_go:stable   "/usr/bin/beacond -l…"   beacond
blockcastd                           blockcast/cdn_gateway_go:stable   "/usr/bin/blockcastd…"   blockcastd
control_proxy                        blockcast/cdn_gateway_go:stable   "/usr/bin/control_pr…"   control_proxy
```
Check logs:
```bash
docker compose logs -fn 100
```
* skip logs if you have all containers running.

---

## Register Node
Get location:
```bash
curl -s https://ipinfo.io | jq '.city, .region, .country, .loc'
```

Generate Node Data & Register:
```bash
docker compose exec blockcastd blockcastd init
```
* Copy and paste the `Registration URL` from the terminal in browser to open the Dashboard.
* With your Hardware ID and Challenge Key pre-filled, Fill-in your location from previous command.
* Register your Node.

![image](https://github.com/user-attachments/assets/9a519702-5565-428a-b79a-bc247a0e370a)

* Wait a few minutes until your node truns **Online**

* Do other socials and add the reward.
![image](https://github.com/user-attachments/assets/c9ffadf3-4e50-4d8b-8de2-54a1ee581504)



