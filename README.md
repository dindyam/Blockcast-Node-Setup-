# Blockcast-Node-Setup-
![image](https://github.com/user-attachments/assets/e788870e-63da-4de0-bd49-df3e90125b13)

[Link to previous Guide](https://x.com/mztacat/status/1846572188574302374?t=G0_H-g6WTnSn2NMIDehTYw&s=19)

# Setting up NODE 
### I already have a node running so I just used it to run this (Killing two birds with a stone) 

------
### Access Platform [HERE](https://app.blockcast.network?referral-code=c8uIyh)
-------
 * Signup with email on Blockcast
 * Connect spare Wallet (SOL)
 * Bind  Twitter and Discord .
 * Complete  quest in profile dashboard.


## Node Installation 
### Supports Ubuntu Linux + Docker-based systems.

🔧 Requirements [ Minimum 2 CPU cores and 4GB RAM ] 
+ Docker & Docker Compose installed
+ Basic terminal knowledge
+ Open ports (if behind NAT) 
-------

### Update system & dependencies 
```
sudo apt update && sudo apt upgrade -y
```

```
sudo apt install ca-certificates curl gnupg lsb-release -y
```

### Add Docker Key & Install 
```
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

```

```
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
  https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

```
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io docker-compose-plugin -y
```

### Enable and start Docker 
```
sudo systemctl enable docker
sudo systemctl start docker
```


### Verify Installation
```
docker --version
docker compose version
```

### Clone Blockcast Repo 
```
git clone https://github.com/Blockcast/beacon-docker-compose.git
cd beacon-docker-compose
```

### Run Node 
```
docker compose up -d
```
![image](https://github.com/user-attachments/assets/484f3a4a-73fb-4fd5-ac65-205738039ce5)


### Check running container 
```
docker ps
```
![image](https://github.com/user-attachments/assets/4ef4d547-5ab2-41d2-8876-1b0da80b4e7b)


### Get Hardware ID & Challenge Key
Run this command to generate the values:
```
docker compose exec blockcastd blockcastd init
```

### You'll see output like `Hardware ID: your-hardware-id` and `Challenge Key: your-challenge-key`


## Register Your Node
* Visit Blockcast Website
* Signup/sign in using email
* Click the Manage Node and Register Node
* Paste your Hardware ID and Challenge Key
![image](https://github.com/user-attachments/assets/6199c816-d925-414b-b86f-a5a9f3c1c8dd)

### SUBMIT AND DONE! 

# Notes
	
 + Your node should remain online 24/7 to be eligible for rewards.
 + Use a VPS or cloud server if needed (e.g., Hetzner, Contabo).




