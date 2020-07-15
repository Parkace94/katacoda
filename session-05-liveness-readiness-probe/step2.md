2. Run following commands to navigate yourself to file directory with `example-liveness-readiness.yaml` file.

    `cd /usr/local/bin/`{{execute}}

    Run list commands to see if file is there:
  
    `l`{{execute}}

    Run cat command to view content of the file:

    `cat example-liveness-readiness.yaml`{{execute}}

    - The pod has a single `Container`.
    - The `periodSeconds` specifies the kubelet should perform a liveness probe every 5 seconds.
    - The `initialDelaySeconds` specifies the kubelet should wait 5 seconds before performing first liveness probe.

    >**NOTE**: The kubelet executes the command `cat /tmp/healthy` in the target container to perform a probe. It will return 0 if the probe performs successfully, if not it returns a non-zero value and the kubelet kills the container and restarts it.

    >**NOTE**: To show working liveness probe, `/bin/sh -c "touch /tmp/healthy; sleep 30; rm -rf /tmp/healthy; sleep 600"` is added to arguments. When the container starts, it will execute this command. Liveness probe will run `cat /tmp/healthy` every 5 seconds to check whether this container is healthy or not. After 30 seconds of container deployment, second part of argument will be triggered and remove `/tmp/healthy` file which makes container `unhealthy` and returns a non-zero value.

    >**Readiness probe**: Readiness probes are configured similarly to liveness probe, only difference is you use `readinessProbe` instead of `livenessProbe`.