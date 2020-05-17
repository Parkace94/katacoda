Start minikube cluster and enable the ingress controller
1. Run following command to view content of the `example-node-selector.yaml`

    `cat example-node-selector.yaml`{{execute}}

    >**NOTE** For this yaml file, it has `nodeSelector: disktype: sdd` this will determine which node this yaml will be deployed.

2. Run kubectl commands to apply the yaml file:

    `kubectl apply -f example-node-selector.yaml`{{execute}}

3. Run following commands to check if deployment was successful.

    `kubectl get pods -o wide`{{execute}}

    >**NOTE**: You can see current deployment is still pending, this is because it did not find any nodes labeled with `disktype: ssd`.

4.  Run following commands to check labels on selected node and add the missing label:

    `kubectl get nodes --show-labels`{{execute}}

    >**NOTE**: From the `LABELS` column, `disktype: sdd` label is missing which our deployment is looking for.

    Run following commands to add the labels, and run `--show-labels` command above after:

    `kubectl label nodes minikube disktype=ssd`{{execute}}

    >**NOTE**: Now `disktype: ssd` label is added to your node.

5.  Verfiy if configured deployment is working:
   
    `kubectl get pods -o wide`{{execute}}