2. Run following command to view content of the `example-replica-set.yaml`

    Navigate and list the files in the file directory

    `cd /usr/local/bin/`{{execute}}

    Run list commands to see if file is there:

    `l`{{execute}}

    Run cat to view the content of the file

    `cat example-replica-set.yaml`{{execute}}

    >**NOTE**: `replicas` under `spec:` determines how many replicas you will be creating when this yaml is deployed to your cluster.

    >**NOTE**: Replicated pods will have randomly generated letters at the end of designated name.

3. Run kubectl commands to apply the yaml file:

    `kubectl apply -f example-replica-set.yaml`{{execute}}