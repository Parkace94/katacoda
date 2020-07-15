3. Run kubectl commands to apply the yaml file:

    `kubectl apply -f example-liveness-readiness.yaml`{{execute}}

4. Run following commands to check the status

    View overall pod deployment

    `kubectl get pod liveness --watch`{{execute}}

    >For first 30 seconds, no error will show.
    >After 30 seconds, a warning status will be shown and will start to kill and recreate the pod. Once recreate is complete, `RESTARTS` count will go up by one.
    >This is infinite loop of killing and recreating pod, `--watch` command will capture and update on each restarts (approximately every 60~90 seconds).
    >To exit, hold `ctrl+c` from your keyboard.

    View details of the pod deployment
  
    `kubectl describe pod liveness`{{execute}}