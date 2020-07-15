4. Run following commands to deploy 50 replicas:

    Run kubectl command to deploy the yaml file

    `kubectl apply -f example-replica-set.yaml`{{execute}}

    View ReplicaSet being deployed

    `kubectl get pod --watch`{{execute}}

    >You can see all pods' status change: Pending, ContainerCreating, and Running.
    >This will take about 60 seconds to complete.
    >Hold `Ctrl+c` to exit out of the --watch view.

    View deployed ReplicaSet status

    `kubectl get rs`{{execute}}

    >You can see number of replica pods deployed: 50.

    View name of each replicated pods

    `kubectl get pod`{{execute}}
    
    >Each pod has different letters at the end of the name.