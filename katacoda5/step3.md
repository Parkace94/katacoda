Create an ingree resource in your cluster.
1. Run following commands to start your Minikube session:

    `minikube start`{{execute}}

    >**About ReplicaSet**:
        - Main purpose is to maintain a stable set of replica pods running at all time. This guarantees the availability of a specific number of identical pods in the cluster.
        - Number of replicas indicates how many pods it should have.
        - A ReplicaSet will create or delete pods as needed to reach the desired ReplicaSet value.

2. Run following command to view content of the `example-replica-set.yaml`

    `cat example-replica-set.yaml`{{execute}}

    >**NOTE**: `replicas` under `spec:` determines how many replicas you will be creating when this yaml is deployed to your cluster.

3. Run kubectl commands to apply the yaml file:

    `kubectl apply -f example-replica-set.yaml`{{execute}}

4. Run following commands to see 3 deployments are complete.

    `kubectl get rs`{{execute}}

    `kubectl get pod`{{execute}}

    >**NOTE**: You can see both rs and pod has 3 different deployments completed.

5. Run following command to see details of the deployment:

    `kubectl describe rs/frontend`{{execute}}