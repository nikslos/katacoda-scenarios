Learn how to work with a single node kubernetes-cluster and deploy your first application.

`minikube start`{{execute HOST1}}

## DEPLOY YOUR FIRST APP
EXAMPLE APP for Deployment:
`kubectl run http --image=katacoda/docker-http-server:latest --replicas=1`{{execute}}

## CHECK IF YOUR DEPLOYMENT WAS SUCCESSFUL:

`kubectl get pods`{{execute}}


`kubectl describe pod`{{execute}}

## TROUBLESHOOTING

List your nodes

`kubectl get nodes`{{execute HOST1}}

Check all your kubernetes components:

`kubectl get pods --all-namespaces`{{execute HOST1}}

Details of your deployment:

`kubectl describe pod [PODNAME]`{{execute HOST1}}

