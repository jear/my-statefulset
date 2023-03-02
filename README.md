```
k create ns my-statefulset
k apply -f jear-secret.yaml -n my-statefulset
k apply -f ssh-key-secret.yaml -n my-statefulset
k apply -f remote-ssh-statefulset.yaml -n my-statefulset
k apply -f remote-ssh-svc.yaml -n my-statefulset
k get svc
kubectl patch svc remote-ssh -n my-statefulset -p '{"spec": {"type": "LoadBalancer"}}'
k get svc
ssh ubuntu@10.69.41.71
```

```
# kubectl create secret generic ssh-key-secret --from-file=ssh-privatekey=/home/ubuntu/.ssh/id_rsa --from-file=ssh-publickey=/home/ubuntu/.ssh/id_rsa.pub
# k get secrets ssh-key-secret -o yaml > ssh-key-secret.yaml

```
