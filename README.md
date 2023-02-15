```
k apply -f jear-secret.yaml 
# kubectl create secret generic ssh-key-secret --from-file=ssh-privatekey=/home/ubuntu/.ssh/id_rsa --from-file=ssh-publickey=/home/ubuntu/.ssh/id_rsa.pub 
# k get secrets ssh-key-secret -o yaml > ssh-key-secret.yaml
k apply -f ssh-key-secret.yaml 
k apply -f remote-ssh-statefulset.yaml 
k apply -f remote-ssh-svc.yaml 
k get svc
kubectl patch svc remote-ssh -n default -p '{"spec": {"type": "LoadBalancer"}}'
k get svc
ssh ubuntu@10.69.41.71
```
