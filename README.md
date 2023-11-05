# k8s
kubectl get pods - посмотреть список подов
kubectl get pods -o wide - посмотреть список подов с расширенной информацией
kubectl discribe pod nginx - посмотреть список подов
kubectl create -f nginx.yaml - создать объект из manifes файла
kubectl run nginx --image=nginx - создать под
kubectl run nginx --image=nginx --dry-run=client -o yaml > nginx.yaml - создать yaml manifest
kubectl delete pod nginx - удалить pod
