Start minikube cluster and enable the ingress controller
1. Run following commands to start your Minikube session:

    `minikube start`{{execute}}

Note: May need to run the following commands
- brew install helm
- helm repo add stable https://kubernetes-charts.storage.googleapis.com/

2. Create the monitor-system namespace

    `kubectl create namespace monitor-system`{{execute}}

3. Install stable helm chart of prometheus operator:

    `helm install prom-op stable/promtheus-operator -n monitor-system`{{execute}}

    >**Note**: This may take up to a minute.

4. Run following commands to verify helm chart successfully installed

    `helm ls`{{execute}}

    `kubectl get pods -n monitor`{{execute}}