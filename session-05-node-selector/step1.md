1. Run following commands to start your Minikube session:

    `minikube start`{{execute}}

    >**About Node Selector**:
        - nodeSelector is the simplest recommended form of node selection constraints.
        - For the pod to be eligible to run on a node, the node must have matching labels.

2. Run following commands to view content of the `example-node-selector.yaml`
   
    - Navigate and list the files in the file directory

    `cd /usr/local/bin/`{{execute}}

    `l`{{execute}}

    - View the `example-node-selector.yaml`

    `cat example-node-selector.yaml`{{execute}}

    >**NOTE**: At the bottom of this yaml file has node selector configured called `nodeSelector: k8s: bootcamp`. With the node selector, this pod will look for the label `k8s=bootcamp` through your nodes before its deployment. The deployment status will be `pending` until it finds the matching label in your node(s).

3. Run kubectl commands to apply the yaml file:

    `kubectl apply -f example-node-selector.yaml`{{execute}}

    - Verify that the pod is running on your cluster

    `kubectl get pods -o=wide`

    >**NOTE**: You can see the status of this pod is `pending`. This is because none of the nodes in this cluster has label called `k8s=bootcamp`.

4. Now we are going to add label to our node.

    - Add labels to our node
    `kubectl label nodes minikube k8s=bootcamp`{{execute}}

    >**NOTE**: This command is adding label `k8s=bootcamp` to node called `minikube`.

    - Check the status of pod again

    `kubectl get pods -o=wide`

    >**NOTE**: Now you can see the pod starts to building.