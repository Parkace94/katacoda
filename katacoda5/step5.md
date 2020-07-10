1. Run following command to view content of the `example-horizontal-pod-autoscalar.yaml`

    `example-horizontal-pod-autoscalar.yaml`{{execute}}

2. Run kubectl commands to apply the yaml file:

    `kubectl apply -f example-horizontal-pod-autoscalar.yaml`{{execute}}

3. Run following commands to check if deployment was successful.

    `kubectl autoscale deployment php-apache --cpu-percent=50 --min=1 --max=10`{{execute}}

    `kubectl get hpa`{{execute}}

4.  Run following commands to check labels on selected node and add the missing label:

    `kubectl get nodes --show-labels`{{execute}}

    >**NOTE**: From the `LABELS` column, `disktype: sdd` label is missing which our deployment is looking for.

    Run following commands to add the labels, and run `--show-labels` command above after:

    `kubectl label nodes minikube disktype=ssd`{{execute}}

    >**NOTE**: Now `disktype: ssd` label is added to your node.

5.  Verfiy if configured deployment is working:
   
    `kubectl get pods -o wide`{{execute}}