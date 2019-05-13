Make your first steps with a single node kubernetes-cluster and deploy an example application.
To create a kubernetes cluster one of the easiest ways is to use minikube. To create your cluster execute:

`minikube start`{{execute HOST1}}

After your kubernetes is up check if your cluster is running correctly. 
`kubectl cluster-info`{{execute HOST1}}

To get full details about your cluster try adding "dump"

Check if your nodes are up
`kubectl get nodes`{{execute HOST1}}

Check all your kubernetes components:

`kubectl get pods --all-namespaces`{{execute HOST1}}

## Deploy your first POD
Use this as an example app for your first deployment:
`kubectl run http --image=katacoda/docker-http-server:latest --replicas=1`{{execute}}

Investigate your deployment is your container "RUNNING", still "WAITING" or "TERMINATED"?

`kubectl get pods`{{execute}}

`kubectl describe pod`{{execute}}

