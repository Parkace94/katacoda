Deploy a simple application.
1. Run following commands to create a Hello-World application:

    `kubectl run web --image=gcr.io/google-samples/hello-app:1.0 --port=8080`{{execute}}

2. Expose the Deployment application.

    `kubectl expose deployment web --target-port=8080 --type=NodePort`{{execute}}

3. Verify the deployed service using kubectl command:

    `kubectl get service web`{{execute}}

4. Export the NodePort:

    `minikube service web --url`{{execute}}

>**NOTE**: at the top of the terminal panel click the plus sign next to terminal, click `Select port to view on Host 1`, and enter the node port of the web service.