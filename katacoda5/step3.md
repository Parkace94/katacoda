Create an ingree resource in your cluster.
1. Run following command to view content of the `example-replica-set.yaml`

    `cat example-replica-set.yaml`{{execute}}

    >**NOTE**: `replicas` under `spec:` determines how many replicas you will be creating when this yaml is deployed to your cluster.

2. Run kubectl commands to apply the yaml file:

    `kubectl apply -f example-replica-set.yaml`{{execute}}

3. Run following commands to see 3 deployments are complete.

    `kubectl get rs`{{execute}}

    `kubectl get pod`{{execute}}

    >**NOTE**: You can see both rs and pod has 3 different deployments completed.

4. Run following command to see details of the deployment:

    `kubectl describe rs/frontend`{{execute}}