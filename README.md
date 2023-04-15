
# Docker & K8s deployment

We will create two pods deployment in Kubernetes, mongodb with internal service and mongo-express whthin external service. A secret that contains DB user and DB password and a configmap that contains DB url and we will reference both inside the deployment.yaml file environment variable. Once we get everything setup, we need our mongo-express eccess to a browser which will use the external service to talk to the pod. The URL will be the IP address of Node and the Port of external service.


## Acknowledgements

 - [Awesome Readme Templates](https://awesomeopensource.com/project/elangosundar/awesome-README-templates)
 - [Awesome README](https://github.com/matiassingers/awesome-readme)
 - [How to write a Good readme](https://bulldogjob.com/news/449-how-to-write-a-good-readme-for-your-github-project)


## Documentation

[Documentation](https//wwww.youtube.com/watch?v=bhBSInQcq2k&t=1475s)
https//kubernetes.io/docs/concepts/overview



## Deployment

To deploy this project run

Mongo Service

```bash
  $ echo -n 'username' | based64
  $ echo -n 'password' | based64
  $ kubectctl apply - f mongo-seceret
  $ kubectctl get seceret
```
MongoDB Deployment

```bash
  $ kubectctl apply -f mongodb.yaml
  $ kubectctl get pod
  $ kubectctl get pod --watch
  $ kubectctl get service
  $ kubectctl describe service mongodb-service
  $ kubectctl get pod -o wide
  $ kubectctl gat all | grep mongo
```
Mongo Configmap

```bash
   $ kubectctl apply -f mongo-configmap.yaml
```
Mongo express Deployment

```bash
   $ kubectctl apply -f mongo-express.yaml
   $ kubectctl get pods
   $ kubectctl get service
```
Mongo express external service

```bash
   $ kubectctl apply -f mongo-express.yaml
   $ kubectctl get service.
```
Minikube Service

```bash
   $ minikube service mongo-express-service
```


