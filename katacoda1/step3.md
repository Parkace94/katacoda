Create an ingree resource
1. Run following commands to navigate yourself to file directory with `example-ingress.yaml` file, and apply.

`cd /usr/local/bin/`{{execute}}

`cat example-ingress.yaml` {{execute}}

`kubectl apply -f example-ingress.yaml`{{execute}}

2. Run following commands to verify assigned IP address.

`kubectl get ingress`{{execute}}

3. Open `/etc/hosts` file and add `Address` and `Hosts` line to the file (see the below example).

`vi /etc/hosts`{{execute}}

Example: `172.17.0.5 hello-world.info`

4. Verfiy if configured ingress is working.

`curl hello-world.info`{{execute}}