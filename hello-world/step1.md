Make your first steps with a single node kubernetes-cluster and deploy an example application.

`minikube start`{{execute HOST1}}

After your kubernetes is up check if your cluster is running correctly. 
`kubectl cluster-info`{{execute HOST1}}
To get full details about your cluster try adding "dump"

Check if your nodes are up
`kubectl get nodes`{{execute HOST1}}

Check all your kubernetes components:

`kubectl get pods --all-namespaces`{{execute HOST1}}

## DEPLOY YOUR FIRST APP
Use this as an example app for your first deployment:
`kubectl run http --image=katacoda/docker-http-server:latest --replicas=1`{{execute}}

## CHECK IF YOUR DEPLOYMENT WAS SUCCESSFUL:

`kubectl get pods`{{execute}}


`kubectl describe pod`{{execute}}

