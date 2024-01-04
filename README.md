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
### Replication controller(RC): provides high availability, load balancing, scaling pods
- kubectl create -f `file name`: create RC using file
- kubectl get replicationcontroller: get list of RC
### ReplicaSet(RS):
- kubectl create -f `file name`: create RS using file
- kubectl get replicaset: get list of RS
- kubectl replace -f `file name`: apply changes to RS using file
- kubectl scale --replicas=6 -f `file name`: apply change to replicas of RS created by using file and the file
- kubectl delete replicaset `RS name`: delete RS and all underlying PODS

