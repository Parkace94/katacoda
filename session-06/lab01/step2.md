Log into Prometheus by port forwarding

1.  List the services prometheus-operator helm chart created

    `kubectl get services -n monitor-system`{{execute}}

    You should now see a list of all the services
    - Alert Manager
    - Prometheus
    - Grafana
    - and more

2. Port forward the prometheus service

    In order to log into prometheus, the service can be port-forwarded

    `kubectl port-forward service/<service name> -n monitor-system 9090`

3. Lets check out the UI

- Check out the "drop-down" next to `Execute` and copy these PromQL commands into the search bar 
    - instance:node_cpu_utilisation:rate1m
    - cluster:node_cpu:sum_rate5m
    - node_memory_MemFree_bytes
    - :node_memory_MemAvailable_bytes:sum
    - container_network_transmit_bytes_total

Notice how there are so many types of metrics prometheus provides to gain insight into your cluster

4. Go to the "Status" drop-down, lets take a look at some of these options

- Runtime and Build Information
    - Get all of your details about your prometheus installation
- Configuration
    - Provides the YAML values of how prometheus was configured by default
    - This is what Helm charts reads and inserts into your prometheus-operator install
    - Pro-Tip: copy this file into version control with a date, if you have any issues you can do a diff to compare what changed
- Targets
    - Shows you all the containers running in your current environment
- Service Discovery
    - Basic overview of your applications or services running in your current environment