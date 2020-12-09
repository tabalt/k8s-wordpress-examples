# K8s WordPress Example

### Install

```
kubectl apply -f examples/mysql-statefulset.yaml
kubectl apply -f examples/wordpress-deployment.yaml
```

### Test

```
kubectl get ingress
kubectl get svc
kubectl get deployment
kubectl get statefulset
kubectl get pods
kubectl exec -it wordpress-xxx-yyy bash # replace pod name
```

### Visit

```
kubectl get ingress wordpress-ingress | grep 'wordpress-ingress' | awk '{print $3" wp.test.com";}' | xargs echo >> /etc/hosts
cat /etc/hosts

curl http://wp.test.com
```