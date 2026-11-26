
# ==========================================
# EXPERIMENT 12: AWS EC2 DOCKER DEPLOYMENT
# ==========================================

# STEP 1: CONNECT TO UBUNTU EC2
# AWS Console -> EC2 -> Instances -> Select Ubuntu
# Connect -> EC2 Instance Connect -> Connect


# STEP 2: UPDATE UBUNTU AND INSTALL SOFTWARE

# Update Ubuntu packages
sudo apt update

# Install Docker
sudo apt-get install docker.io -y

# Install Git
sudo apt install git -y

# Install Nano text editor
sudo apt install nano -y


# STEP 3: CLONE MAVEN WEB PROJECT

# Clone project from GitHub
git clone YOUR_MAVEN_WEB_GITHUB_URL

# Enter project directory
cd YOUR_PROJECT_FOLDER

# Display project files
ls


# STEP 4: CREATE DOCKERFILE

# Create Dockerfile
nano Dockerfile

# Paste the following content inside Dockerfile:

# FROM tomcat:9.0
# COPY target/MavenWeb.war /usr/local/tomcat/webapps/ROOT.war
# EXPOSE 8080
# CMD ["catalina.sh", "run"]

# Save: Ctrl + O -> Enter -> Ctrl + X


# STEP 5: CONFIGURE DOCKER PERMISSIONS

# Add Ubuntu user to Docker group
sudo usermod -aG docker ubuntu

# Refresh group permissions
newgrp docker

# Check Docker access
docker ps


# STEP 6: BUILD DOCKER IMAGE

# Build image from Dockerfile
docker build -t mavenweb .

# Display available Docker images
docker images


# STEP 7: RUN DOCKER CONTAINER

# Run container in background
# Map EC2 port 6060 to Tomcat port 8080
docker run -d --name app-demo -p 6060:8080 mavenweb

# Display running containers
docker ps

# View container logs
docker logs app-demo


# STEP 8: CONFIGURE AWS SECURITY GROUP
# AWS Console -> EC2 -> Instances -> Select Ubuntu
# Security -> Click Security Group
# Edit inbound rules -> Add rule:
# Type: Custom TCP
# Port: 6060
# Source: 0.0.0.0/0
# Save rules


# STEP 9: ACCESS APPLICATION
# Open browser and enter:
# http://YOUR_PUBLIC_IP:6060

# Example:
# http://98.93.222.176:6060

# Expected output: Hello World
