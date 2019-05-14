Learn how to work with a kubernetes-cluster and deploy your first application.

We want to deploy a workpress application. 
We will need two pods, one with a container running wordpress on an apache webserver and one with a container running a mysql database. 

## Test the durability of the deployment

Delete the wordpress pod and check the behaviour of the application. 

Does it still work?


## Scaleability of Deployments

When the load increases on an application it makes sense to deploy multiple instances of an application. 

To do this, set the replicas of the application to 3 instances. Check the pods for two new ones. 


Hint: You might need some changes in the yaml
`spec:
    replicas: 3
`


## Injection of secrets

Credentials are an important factor in modern applications. Normally it is not a good idea to store them plain text inside of configuration files. 

It is possible to use kubernetes to manage the credentials and inject them into the pods and applications. 

To use a password in a secret it should be stored base64-encoded. 

`echo -n '1f2d1e2e67df' | base64`
MWYyZDFlMmU2N2Rm

You can create a secret with a yaml file which looks something like this

`apiVersion: v1
kind: Secret
metadata:
  name: mysecret
type: Opaque
data:
  username: YWRtaW4=
  password: MWYyZDFlMmU2N2Rm
`

This secret can be injected into an application with the following structure
```
spec:
  containers:
  - name: mycontainer
    image: redis
    env:
      - name: SECRET_USERNAME
        valueFrom:
          secretKeyRef:
            name: mysecret
            key: username
      - name: SECRET_PASSWORD
        valueFrom:
          secretKeyRef:
            name: mysecret
            key: password
```

Now you should try to create a secret for the mysql-password and use it for the wordpress and mysql deployments. 

