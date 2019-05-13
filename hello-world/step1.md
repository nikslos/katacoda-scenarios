Make your first steps with a single node kubernetes-cluster and deploy an example application.
To create a kubernetes cluster one of the easiest ways is to use minikube. To create your cluster execute:

`minikube start`{{execute HOST1}}

After your kubernetes is up interact with your cluster. "kubectl" is the command line interface for running commands against your kubernetes-cluster. It uses a config-file which is located at $HOME/.kube/config. Check if your cluster is running correctly. 

`kubectl cluster-info`{{execute HOST1}}

If your want to get more details about your cluster try adding "dump".

Check if all your nodes are up and healthy.

`kubectl get nodes`{{execute HOST1}}

Let's see which kubernetes components are installed already. Check all your kubernetes components using:

`kubectl get pods --all-namespaces`{{execute HOST1}}

## Deploy your first app on kubernetes

Now we are ready to make our first kubernetes deployment. There are several ways to deploy a container to a kubernetes cluster. One way is to use kubectl.
Use this as an example app for your first deployment:

`kubectl run http --image=katacoda/docker-http-server:latest --replicas=1`{{execute}}

Investigate your deployment is your container "RUNNING", still "WAITING" or "TERMINATED"?

`kubectl get pods`{{execute}}

`kubectl describe pod`{{execute}}

