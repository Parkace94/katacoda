Deploy second simple applications.
1. Run following commands to create a Hello-World application:

`kubectl run web2 --image=gcr.io/google-samples/hello-app:2.0 --port=8080`{{execute}}

2. Expose the Deployment application.

`kubectl expose deployment web2 --target-port=8080 --type=NodePort`{{execute}}

3. Access second version of the sample application:

`curl hello-world.info/v2`{{execute}}

4. Add following lines to existing ingress service:
```
   - path: /v2/*
        backend:
          serviceName: web2
          servicePort: 8080
```

4. `kubectl edit exmaple-ingress.yaml`{{execute}}

5. Access second version of the ample application again:

`curl hello-world.info/v2`{{execute}}

>**NOTE**: at the top of the terminal panel, click the plus sign, and then click Select port to view on Host 1. Enter the NodePort, in this case `31637`, and then click Display Port.