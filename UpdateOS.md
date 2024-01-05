Сделать ноду noSchedulable и выселить все поды
```yaml
kubectl drain node01 --ignore-daemonsets
```
Запретить размещаться новым подам на этой ноде (существующие не будут затронуты)
```yaml
kubectl cordon node01
```
Разрешить размещаться новым подам обратно
```yaml
kubectl uncordon node01
```
Вернуть ноду для возможности Schedulable
```yaml
kubectl uncordon node01
```
Посмотреть план upgrade
```yaml
kubeadm upgrade plan
```
Обновить зависимости
```yaml
apt update
```
Обновить kubadm
```yaml
apt-get install kubeadm=1.27.0-00
```
Обновить конфигурацию kubadm
```yaml
kubeadm upgrade node
```
Обновить kubelet
```yaml
apt-get install kubelet=1.27.0-00 
```
Перезапустить kubelet
```yaml
systemctl daemon-reload
systemctl restart kubelet
```
