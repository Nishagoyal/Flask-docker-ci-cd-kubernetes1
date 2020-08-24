# Flask-docker-ci-cd-kubernetes1
# Overview:
Flask application has been converted into a docker image and stored in container registy using CI/CD pipeline and hosted on aks.

## Steps followed:
1. Create your flask application and its requirements file
2. Create its dockerfile
3. Create a container registry
4. Through CI/CD pipeline , add your docker image to the registry
5. Create an aks cluster 
6. Configure kubectl to connect to your Kubernetes cluster using : az aks get-credentials --resource-group <RG_Name> --name <cluster_Name>
6. Attach your aks with your azure registry using the command: az aks update -n <cluster_Name> -g <RG_Name> --attach-acr [acrName]
7. Check nodes using : kubectl get nodes
8. Run the yaml file which will deploy your docker image using: kubectl apply -f <your file>
9. To monitor progress: kubectl get service <service name> --watch
When the EXTERNAL-IP address changes from pending to an actual public IP address, use CTRL-C to stop the kubectl watch process
## To see your deployed application:
  http://<external ip from step 9>:5000
  



