
Now we are ready to make our first kubernetes deployment. There are several ways to deploy a container to a kubernetes cluster. One way is to use kubectl.
Use this as an example app for your first deployment:

`kubectl run http --image=katacoda/docker-http-server:latest --replicas=1`{{execute}}

Investigate your deployment is your container "RUNNING", still "WAITING" or "TERMINATED"?

`kubectl get pods`{{execute}}

You can get further information about your pod if you use "describe pod [RESOURCE]"

`kubectl describe pod`{{execute}}

Before you continue you have to delete your running POD you can use:

`kubectl delete deployment http`{{execute}}

