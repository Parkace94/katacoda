1. Run following commands to start your Minikube session:

    `minikube start`{{execute}}

    >This process may take up minute or two. If it outputs error, simply perform `minikube start` again.

    ### About Node Selector:
        - nodeSelector is the simplest recommended form of node selection constraints.
        - For the pod to be eligible to run on a node, the node must have matching labels.