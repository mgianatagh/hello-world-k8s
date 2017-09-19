# hello-world-k8s
Hello world application for Kubernetes environment

## Run Hello-World 
This quickstart shows you how to use Google Cloud Shell to deploy a prebuilt Docker container image with a simple web application written in Go.

**Setup**

```
# Set a default compute zone
gcloud config set compute/zone us-east4-c
 
# Get the credentials for the cluster
gcloud container clusters get-credentials cluster-1
 
# Run the container
kubectl run hello-web --image=gcr.io/google-samples/hello-app:1.0 --port=8080
 
# Expose the container
kubectl expose deployment hello-web --type="LoadBalancer"
 
# Copy the external IP address for the hello-web app
kubectl get service hello-web
 
# View the app (replace EXTERNAL-IP with the external IP address you obtained in the previous step)
http://EXTERNAL-IP:8080
```

**Cleanup**
```
# Delete the services you created to remove the load balancing resources that are provisioned to serve them
kubectl delete service hello-web
```