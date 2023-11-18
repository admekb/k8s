* Чтобы убрать taint у ноды можно запустить коману с сущестующими параметрами tain добавив "-"
```console
kubectl taint nodes controlplane node-role.kubernetes.io/control-plane:NoSchedule-
```
kubectl taint nodes controlplane node-role.kubernetes.io/control-plane:NoSchedule-
kubectl taint nodes node01 spray=mortein:NoSchedule
kubectl taint nodes node-name key=value:taint-effect
kubectl get pods --selector env=dev,bu=finance --no=headers | wc -l
kubectl replace --force -f nginx.yaml
kubectl get pods --watch
kubectl get secret postgres-secret-config -o jsonpath="{.data.password}" | base64 --decode
echo "postgres" | base64
python3 -m venv kubespray-venv
source kubespray-venv/bin/activate
pip3 install -U -r requirements.txt
kubectl get componentstatuses
kubectl label node node2 node-role.kubernetes.io/worker=
# k8s
* Обращение к сервису db-service в dev namespace к service svc.cluster.local
```console
db-service.dev.svc.cluster.local
```
* Посмотреть список подов
```console
kubectl get pods
```
* Посмотреть список подов с расширенной информацией
```console
kubectl get pods -o wide
```
* Расширенная информация о поде
```console
kubectl discribe pod nginx
```
* Создать объект из manifest файла
```console
kubectl create -f nginx.yaml
```
* Создать под
```console
kubectl run nginx --image=nginx
```
* Создать yaml manifest
```console
kubectl run nginx --image=nginx --dry-run=client -o yaml > nginx.yaml
```
* Удалить pod
```console
kubectl delete pod nginx
```
* Пересоздать replicaset
```console
kubectl replace -f replica.yml
```
* Пересоздать replicaset с переозданием сущестующих подов
```console
kubectl replace -f replica.yaml --force
```
* Маштабировать replicaset через manifest
```console
kubectl scale --replicas=6 -f replica.yml
```
* Маштабировать replicaset через manifest через name
```console
kubectl scale --replicas=6 replicaset myapp-replicaset
```
* Отобразить replicaset
```console
kubectl get replicaset
```
* Удалить replicaset
```console
kubectl delete replicaset myapp-replicaset
```
* Создать manifest файл из существующей replicaset
```console
kubectl get replicaset new-replica-set -o yaml >> replica.yaml
```
* Посмотреть версию api
```console
kubectl explain replicaset
```
* Отредактировать replicaset
```console
kubectl edit replicaset new-replicaset
```
* Отобразить все объекты
```console
kubectl get all
```






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
