1. Run following commands to start your Minikube session:

    `minikube start`{{execute}}

    >**About Liveness and Readiness probe**:
        - The kubelet uses liveness probes to know when to restart a container.
        - The kubelet uses readiness probes to know when a container is ready to start accepting traffic.
        - The kubelet uses these probes to know when a container application has started. If congainer is not ready, probes will run continously interfering the container start up until probe checks succeeds.

2. Run following commands to navigate yourself to file directory with `example-liveness-readiness.yaml` file.

    `cd /usr/local/bin/`{{execute}}

    Run list commands to see if file is there:
  
    `l`{{execute}}

    Run cat command to view content of the file:

    `cat example-liveness-readiness.yaml`{{execute}}

    - The pod has a single `Container`.
    - The `periodSeconds` specifies the kubelet should perform a liveness probe every 5 seconds.
    - The `initialDelaySeconds` specifies the kubelet should wait 5 seconds before perform first liveness probe.

    >**NOTE**: The kubelet executes the command `cat /tmp/healthy` in the target container to perform a probe. It will return 0 if the probe performs successfully, if not it returns a non-zero value and the kubelet kills the container and restarts it.

    >**NOTE**: To show working liveness probe, `/bin/sh -c "touch /tmp/healthy; sleep 30; rm -rf /tmp/healthy; sleep 600"` is added to arguments. When the container starts, it will execute this command. Liveness probe will run `cat /tmp/healthy` every 5 seconds to check whether this container is healthy or not. After 30 seconds of container deployment, second part of argument will be triggered and remove `/tmp/healthy` file which makes container `unhealthy` and returns a non-zero value.

    >**Readiness probe**: Readiness probes are configured similarly to liveness probe, only difference is you use `readinessProbe` instead of `livenessProbe`.

3. Run kubectl commands to apply the yaml file:

    `kubectl apply -f example-liveness-readiness.yaml`{{execute}}

4. Run following commands to check the status

    `kubectl describe pod liveness`{{execute}}
    `kubectl get pod liveness`{{execute}}

    - For first 30 seconds, no error will show.
    - After 30 seconds, a warning status will be shown and will have 1 restarts.