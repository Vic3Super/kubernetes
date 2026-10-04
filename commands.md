### Basic commands

```
kubectl get pods
kubectl get pods -A
kubectl get pods -n my-app
kubectl get pods -o wide


kubectl get deployments -n my-app
kubectl describe deployment my-app -n my-app

kubectl get services -n my-app
kubectl describe service my-app -n my-app


kubectl port-forward service/my-app 8081:80 -n my-app

http://localhost:8081/
```