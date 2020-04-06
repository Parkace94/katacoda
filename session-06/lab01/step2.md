Minikube dashboard

By design, minikube has a built in dashboard to launch that helps you review all resources in your cluster

1. Log into the minikube cluster

`minikube dashboard`{{execute}}

2. Review the dashboard UI

- See how many namespaces there are
- Review the different cluster roles
    - Review the k8 verbs it has access to
- Change the namespace to monitor and review all its resources

3. View the Custom Resource Definitions (CRDs) in your monitor namespace

- This can help you keep track which CRDs are installed in your namespaces