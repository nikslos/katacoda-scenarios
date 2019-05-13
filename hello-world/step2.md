Learn how to work with a kubernetes-cluster and deploy your first application.

We want to deploy a workpress application. 
We will need two pods, one with a container running wordpress on an apache webserver and one with a container running a mysql database. 

## Deploy wordpress

Start with deploying the wordpress application
`kubectl apply -f <deployment.yaml>`

