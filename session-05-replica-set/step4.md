5. Reduce the number of replicas:
   
    Edit replicas using kubectl edit

    `kubectl edit replicaset frontend`{{execute}}

    >navigate to `replicas: 50` under `specs:` using keyboard arrows and press `i` to start editing.
    >change the number to `5` from `50`
    >press `esc` from your keyboard to leave insert mode and type `:wq`{{execute}} in terminal to save and exit.

    View ReplicaSet being deployed

    `kubectl get pod --watch`{{execute}}

    >You can see 45 pods being terminated.
    >This will take about 90 seconds to complete.
    >Hold `Ctrl+c` to exit out of the --watch view.

    View deployed ReplicaSet status

    `kubectl get rs`{{execute}}

    >You can see number of replica pods deployed: 5.

    View name of remaining replicated pods

    `kubectl get pod`{{execute}}
    
    >Each pod has different letters at the end of the name.

6. Run following command to see details of the deployment:

    `kubectl describe rs/frontend`{{execute}}

    >You can use this to troubleshoot if pod deployment fails.

    - Replicas show the desired and deployed pods.
    - Pod Status shows the status of current pods.
    - Events tab shows each pods were created by replicaset-controller. This will also show any errors if detected.