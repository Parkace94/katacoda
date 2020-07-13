1. Run following commands to start your Minikube session:

    `minikube start`{{execute}}

    >This process may take up minute or two. If it outputs error, simply perform `minikube start` again.

    ### About Liveness and Readiness probe:
    - The kubelet uses liveness probes to know when to restart a container.
    - The kubelet uses readiness probes to know when a container is ready to start accepting traffic.
    - The kubelet uses these probes to know when a container application has started. If container is not ready, probes will run continously interfering the container start up until probe checks succeeds.