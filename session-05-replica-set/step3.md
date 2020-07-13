4. Run following commands to see 3 deployments are complete.

    View the current ReplicaSet deployed

    `kubectl get rs`{{execute}}

    >You can see deployed pod is `3` not `1`.

    View name of each replicated pods

    `kubectl get pod`{{execute}}
    
    >Each pod has different letters at the end of the name.

5. Run following command to see details of the deployment:

    `kubectl describe rs/frontend`{{execute}}

    >You can use this to troubleshoot if pod deployment fails.

    - Replicas show the desired and deployed pods.
    - Pod Status shows the status of current pods.
    - Events tab shows each pods were created by replicaset-controller. This will also show any errors if detected.