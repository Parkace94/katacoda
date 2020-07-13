3. Run kubectl commands to apply the yaml file:

    `kubectl apply -f example-node-selector.yaml`{{execute}}

    Verify that the pod is running on your cluster

    `kubectl get pods -o=wide`{{execute}}

    >**NOTE**: You can see the status of this pod is `pending`. This is because none of the nodes in this cluster has label called `k8s=bootcamp`.

    Check in details

    `kubectl describe pod nginx`{{execute}}

    >**NOTE**: Event section is showing that it failed to schedule because there wasn't any nodes matching the label.

4. Now we are going to add label to our node.

    Add labels to your node
  
    `kubectl label nodes minikube k8s=bootcamp`{{execute}}

    >**NOTE**: This command is adding label `k8s=bootcamp` to node called `minikube`.

    Check the status of pod again

    `kubectl get pods -o=wide`{{execute}}

    >**NOTE**: Now because we added matching label to your node, you can see the pod starts to building.