---
description: A quick guide to set up your exit node
---

# Exit Node Setup Using Docker

## Step 1: Install Docker and Docker-Compose

`Docker` and `docker-compose` are prerequisites to download and run the docker images and container.

Enter the following commands to download and install docker.

```bash
sudo apt update && sudo apt install apt-transport-https ca-certificates curl software-properties-common -y && curl -fsSL 
https://download.docker.com/linux/ubuntu/gpg
 | sudo apt-key add - && sudo add-apt-repository "deb [arch=amd64] 
https://download.docker.com/linux/ubuntu
 focal stable" && sudo apt update && sudo apt install docker-ce -y && sudo systemctl status docker
```

Enter the following commands to download and install docker-compose.

```bash
sudo curl -L "
https://github.com/docker/compose/releases/download/1.28.5/docker-compose-$(uname
 -s)-$(uname -m)" -o /usr/local/bin/docker-compose && sudo chmod +x /usr/local/bin/docker-compose && docker-compose --version
```

## Step 2: Pull the Image From Docker Hub

Enter the following command into the terminal to pull the BelNet Exit Node image from the docker hub.

```bash
docker pull beldex/belnet-exitnode:v2
```

## Step 3: Download & Compose yml File

Enter the following command to get the BelNet yml file from Beldex deb.

```bash
sudo apt install wget && wget 
https://deb.beldex.io/Beldex-projects/Belnet/docker-compose.yml
```

## Step 4: To Run Container

Enter the following command to run the yml file as a container.

```bash
docker-compose up -d
```

## Step 5: Login Into Container

Enter the following command to get the container ID and other details.

```bash
docker ps
```

Enter the following command _after replacing your container ID in place of \<container -id>_

```bash
docker exec -it <container -id> bash
```

## Step 6: To View Exit Node Address

Your exit node is now live. Get your exit node’s BelNet address using the following command.

```bash
host -t cname localhost.bdx 127.3.2.1
```
