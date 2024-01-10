# kubernetes-practice
## CMD basic:
- kubectl cluster-info: get cluster info
- kubectl get nodes: get list nodes
- kubectl get nodes -o wide: get list nods with more info
- kubectl get all: get all created object
  
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
- kubectl describe replicaset `RS name`: get RS detail
- kubectl edit rs `RES name`: edit RS

## CMD Deployment:
### Stategy:
- Recreate:Terminates all the pods and replaces them with the new version
- Rolling: Replaces pods running the old version of the application with the new version without downtime
- Canary: New version is rolled out slowly, creating new replicas replacing the old ones. This involves deploying a new version of the application alongside the old one, with the old version of the application serving most users and the newer version serving a small pool of test users
- A/B: Similar to a Canary deployment, using an A/B deployment, you can target a given subsection of users based on some target parameters (usually the HTTP headers or a cookie)
- Shadow: A new version of an application is deployed alongside the existing production version, primarily for monitoring and testing purposes
- Blue/Green: Deploying the new application version (green) alongside the old one (blue). A load balancer in the form of the service selector object is used to direct the traffic to the new application (green) instead of the old one
### CMD:
- kubectl create -f `file name`: create Deployment using file
- kubectl get deployments: get list of Deployment
- kubectl apply -f `file name`: apply update for deployment
### Update and Rollback
- kubectl rollout status deployment/`name`: get rollout deployment status
- kubectl rollout history deployment/`name`: get rollout deployment history
- kubectl rollout undo deployment/`name`: rollback rollout deployment

## Networking
- Each node has its own IP Address
- Each pod has its own IP Address. Pod's IP adress is unique in 1 node but can be repeated in another node => We need to assign IP for Pod ourselves
- All pods can communicate with another without NAT
- All nodes can communicate with pod and the other way around without NAT

## Serivces
- NodePort: Make internal port accessible on the port of node
- ClusterIP: Create virtual IP inside cluster to enable communication between different POD
- LoadBalancer:
### CMD:
- kubectl create -f `file name`: create Service using file
- kubectl get services: get list of services
