Start minikube cluster and enable the ingress controller
1. Run following commands to start your Minikube session:

    `minikube start`{{execute}}

2. Run following commands to navigate yourself to file directory with `example-liveness-readiness.yaml` file, and apply.

    `cd /usr/local/bin/`{{execute}}

    Run list commands to see if file is there:
  
    `l`{{execute}}

    Run cat command to view content of the file:

    `cat example-liveness-readiness.yaml`{{execute}}

    >**NOTE** For the initial 30 seconds of the deployment, there is `/tmp/healthy`, so there will not be any error but after 30 seconds this will be removed which will return a failure code.

3. Run kubectl commands to apply the yaml file:

    `kubectl apply -f example-liveness-readiness.yaml`{{execute}}

4. Run following commands to verify assigned IP address.

    `kubectl describe pod liveness-exec`{{execute}}

    >**NOTE**: Run the above command minute after to see the difference.