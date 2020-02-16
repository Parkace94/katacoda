Deploy 2 quick simple applications.
1. Run following commands to create a Hello-World application:

`kubectl run web --image=gcr.io/google-samples/hello-app:1.0 --port=8080`{{execute}}

`kubectl run web2 --image=gcr.io/google-samples/hello-app:2.0 --port=8080`{{execute}}

2. Expose the Deployment application.

`kubectl expose deployment web --target-port=8080 --type=NodePort`{{execute}}

`kubectl expose deployment web2 --target-port=8080 --type=NodePort`{{execute}}

3. Verify the service using kubectl command:

`kubectl get service`{{execute}}

4. Export the NodePort:

`minikube service web --url`{{execute}}

>**NOTE**: at the top of the terminal panel, click the plus sign, and then click Select port to view on Host 1. Enter the NodePort, in this case `31637`, and then click Display Port.