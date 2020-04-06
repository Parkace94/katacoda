Log into Grafana

1. Port forward the grafana port

    `k port-forward svc/prom-op-grafana -n monitor 8001:80`{{execute}}

2. Log in with the following credentials (default values)

- user: admin
- paswword: prom-operator

3. Review some of the pre-built dashboards under the `Home` drop-down

    Dashboards to Review
    - Kubernetes/Pods
    - Kubernetes/Networking/Pods
    - Kubernetes/Compute Resources/Pods

4. Complete the tasks below

    - What is the current `CPU Utilization` of your node?
    - What is the `Memory Utilization` of your cluster?
    - How many pods are currently running in `kube-system`?
    - How many pods are currently running in `monitor`
    - What is the `Average Rate of Bytes` transmitted for namespace=monitor?

5. Find custom dashboards to import

    You can download community built dashboards from `grafana.com/dashboards`

    - Go to grafana.com/dashboards
    - In left pane, change data source to prometheus
    - In search bar, type `kubernetes`
    - Select `Cluster Monitoring for Kubernetes` and copy the ID
        - ID: 10000

    Note: You can copy the ID or the JSON file to import in your grafana environment

6. Import the custom dashboard

    - In the left pane of grafana hit the plus sign (+)
    - Select Import
    - Copy ID from step 5 into
        - Name: keep the default name
        - Folder: General
        - UID: randomly generate
        - DataSource: Prometheus
    - Hit import