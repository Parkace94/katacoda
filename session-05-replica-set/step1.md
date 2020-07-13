>It's going to take few minutes to have kubernetes to start.

### About ReplicaSet:
- Main purpose is to maintain a stable set of replica pods running at all time. This guarantees the availability of a specific number of identical pods in the cluster.
- Number of replicas indicates how many pods it should have.
- A ReplicaSet will create or delete pods as needed to reach the desired ReplicaSet value.