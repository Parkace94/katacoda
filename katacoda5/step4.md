Deploy second simple applications.
1. Run following commands to create another Hello-World application:

    `kubectl run web2 --image=gcr.io/google-samples/hello-app:2.0 --port=8080`{{execute}}

2. Expose the Deployment application.

    `kubectl expose deployment web2 --target-port=8080 --type=NodePort`{{execute}}

3. Access second version of the sample application:

    `curl hello-world.info/v2`{{execute}}

4. Add following lines to existing ingress service:

    `kubectl edit exmaple-ingress.yaml`{{execute}}

    ```
    - path: /v2/*
        backend:
            serviceName: web2
            servicePort: 8080
    ```

5. Access second version of the ample application again:

    `curl hello-world.info/v2`{{execute}}