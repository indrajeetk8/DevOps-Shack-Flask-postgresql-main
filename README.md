#!/bin/bash

# Update & Upgrade System Packages
sudo apt update -y
sudo apt upgrade -y

# Install Docker & Docker Compose
sudo apt install -y docker.io
sudo systemctl start docker
sudo systemctl enable docker
sudo apt install -y docker-compose

# Verify Installation
docker --version
docker-compose --version
systemctl status docker

# Clone the Repository
git clone https://github.com/indrajeetk8/DevOps-Shack-Flask-postgresql-main.git
ls
cd DevOps-Shack-Flask-postgresql-main/
ls
ll  # Optional: List files in detail

# Build & Run Docker Containers
sudo docker-compose up --build

# Verify Running Containers
sudo docker ps

# Access Running Container (Replace with actual container ID)
sudo docker exec -it $(sudo docker ps -q | head -n 1) /bin/bash

# Stop & Remove Containers
sudo docker-compose down
