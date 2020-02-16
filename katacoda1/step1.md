Enable the ingress controller
1. Run following commands to start your Minikube session:
   
`minikube start`{{execute}}

2. To enable the NGINX Ingress controller, run the following command:

`minikube addons enable ingress`{{execute}}

>**Note**: This may take up to a minute.

3. Run following commands to verify that the NGINX Ingress controller is enabled and running:

`kubectl get pods -n kube-system`{{execute}}