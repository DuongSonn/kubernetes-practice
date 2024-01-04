# kubernetes-practice
## CMD basic:
- kubectl cluster-info: get cluster info
- kubectl get nodes: get list nodes
- kubectl get nodes -o wide: get list nods with more info
  
## CMD Pod:
- kubectl run `pod name`: deploy pod
- kubectl run `pod name` --image=`image name`: deploy pod with image
- kubectl get pods: get list pods
- kubectl get pods -o wide: get list pods with more info
- kubectl describe pod `pod name`: get pod detail
- kubectl delete pod `pod name`: delete pod
- kubectl edit pod `pod name`: edit pod
- kubectl create -f `file name`: deploy pod using yaml file
- kubectl run `pod name` --image=`image name` --dry-run=client -o yaml > `file name`.yaml: deploy pod with image and export yaml
- kubectl apply -f `file name`: apply changes to pod using yaml file

## CMD ReplicaSets:
### Replication controller: provides high availability, load balancing, scaling

