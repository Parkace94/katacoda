2. Run following commands to view content of the `example-node-selector.yaml`
   
    Navigate and list the files in the file directory

    `cd /usr/local/bin/`{{execute}}

    Run list commands to see if file is there:

    `l`{{execute}}

    View the `example-node-selector.yaml`

    `cat example-node-selector.yaml`{{execute}}

    >**NOTE**: At the bottom of this yaml file has node selector configured called `nodeSelector: k8s: bootcamp`. With the node selector, this pod will look for the label `k8s=bootcamp` through your nodes before its deployment. The deployment status will be `pending` until it finds the matching label in your node(s).