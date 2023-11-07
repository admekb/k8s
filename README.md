# k8s
kubectl get pods - посмотреть список подов
kubectl get pods -o wide - посмотреть список подов с расширенной информацией
kubectl discribe pod nginx - посмотреть список подов
kubectl create -f nginx.yaml - создать объект из manifes файла
kubectl run nginx --image=nginx - создать под
kubectl run nginx --image=nginx --dry-run=client -o yaml > nginx.yaml - создать yaml manifest
kubectl delete pod nginx - удалить pod
kubectl replace -f replica.yml
kubectl scale --replicas=6 -f replica.yml
kubectl scale --replicas=6 replicaset myapp-replicaset
kubectl get replicaset
kubectl delete replicaset myapp-replicaset
kubectl get replicaset new-replica-set -o yaml >> replica.yaml
kubectl replace -f replica.yaml --force
kubectl explain replicaset - посмотреть версию api
kubectl edit replicaset new-replicaset
kubectl get all

Create an NGINX Pod

kubectl run nginx --image=nginx

Generate POD Manifest YAML file (-o yaml). Don’t create it(–dry-run)

kubectl run nginx --image=nginx --dry-run=client -o yaml

Create a deployment

kubectl create deployment --image=nginx nginx

Generate Deployment YAML file (-o yaml). Don’t create it(–dry-run)

kubectl create deployment --image=nginx nginx --dry-run=client -o yaml

Generate Deployment YAML file (-o yaml). Don’t create it(–dry-run) and save it to a file.

kubectl create deployment --image=nginx nginx --dry-run=client -o yaml > nginx-deployment.yaml

Make necessary changes to the file (for example, adding more replicas) and then create the deployment.

kubectl create -f nginx-deployment.yaml

OR

In k8s version 1.19+, we can specify the –replicas option to create a deployment with 4 replicas.

kubectl create deployment --image=nginx nginx --replicas=4 --dry-run=client -o yaml > nginx-deployment.yaml
