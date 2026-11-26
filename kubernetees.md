
# ==========================================
# 1. START MINIKUBE
# ==========================================

# Start Kubernetes cluster using Docker driver
minikube start --driver=docker

# Check Minikube status
minikube status

# Display Kubernetes cluster nodes
kubectl get nodes


# ==========================================
# 2. CREATE NGINX DEPLOYMENT
# ==========================================

# Create a deployment named mynginx using Nginx image
kubectl create deployment mynginx --image=nginx

# Display all deployments
kubectl get deployments

# Display all pods
kubectl get pods

# Display detailed information about pods
kubectl describe pods


# ==========================================
# 3. EXPOSE NGINX DEPLOYMENT
# ==========================================

# Expose deployment using NodePort service
# Port 80 is exposed and forwarded to container port 80
kubectl expose deployment mynginx --type=NodePort --port=80 --target-port=80

# Display all services
kubectl get services


# ==========================================
# 4. SCALE NGINX DEPLOYMENT
# ==========================================

# Scale deployment to 4 replicas (4 pods)
kubectl scale deployment mynginx --replicas=4

# Verify the four pods
kubectl get pods

# Check deployment details
kubectl get deployments


# ==========================================
# 5. OPTIONAL DASHBOARD
# ==========================================

# Open Minikube dashboard
minikube dashboard

# Display pods from all namespaces
kubectl get pods -A
