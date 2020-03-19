Create an ingree resource in your cluster.
1. Run following commands to navigate yourself to file directory with `example-ingress.yaml` file, and apply.

    `cd /usr/local/bin/`{{execute}}

    Run list commands to see if file is there:
  
    `l`{{execute}}

    Run cat command to view content of the file:

    `cat example-ingress.yaml`{{execute}}

2. Run kubectl commands to apply the yaml file:

    `kubectl apply -f example-ingress.yaml`{{execute}}

3. Run following commands to verify assigned IP address.

    `kubectl get ingress`{{execute}}

    >**NOTE**: Take note of IP address of the ingress. This process may take up to few minutes.

4. Open `/etc/hosts` file and add `Address` and `Hosts` line to the file (see the below example).

    `vi /etc/hosts`{{execute}}

    >**Example**: `172.17.0.5 hello-world.info`

5. Verfiy if configured ingress is working.

    `curl hello-world.info`{{execute}}

    >**Example**: 
        Hello, world!
        Version: 1.0.0
        Hostname: web-6d456746d-drfjc