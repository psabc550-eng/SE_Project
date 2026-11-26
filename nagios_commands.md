
# ==========================================
# EXPERIMENT: NAGIOS USING DOCKER
# ==========================================

# STEP 1: Download Nagios Docker image
# Downloads the Nagios image from Docker Hub
docker pull jasonrivers/nagios:latest


# STEP 2: Run Nagios container
# Creates and starts a container named nagiosdemo
# -p 8888:80 maps host port 8888 to container port 80
docker run --name nagiosdemo -p 8888:80 jasonrivers/nagios:latest


# STEP 3: Access Nagios Dashboard
# Open this URL in your browser:
# http://localhost:8888
#
# Login credentials:
# Username: nagiosadmin
# Password: nagios


# STEP 4: Check container status

# Displays currently running containers
docker ps

# Displays all containers, including stopped containers
docker ps -a


# STEP 5: View Nagios logs

# Displays container logs
docker logs nagiosdemo

# Displays logs continuously in real time
docker logs -f nagiosdemo


# STEP 6: Stop Nagios container

# Stops the running Nagios container
docker stop nagiosdemo


# STEP 7: Start Nagios container again

# Starts the previously stopped container
docker start nagiosdemo

# Checks whether the container is running
docker ps


# STEP 8: Remove Nagios container

# Stop the container before removing it
docker stop nagiosdemo

# Removes the stopped container
docker rm nagiosdemo


# STEP 9: Remove Nagios image (Optional)

# Displays all downloaded Docker images
docker images

# Removes the Nagios image from the system
docker rmi jasonrivers/nagios:latest
