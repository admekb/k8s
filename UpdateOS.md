Сделать ноду noSchedulable и выселить все поды
```yaml
kubectl drain node01 --ignore-daemonsets
```
Запретить размещаться новым подам на этой ноде (существующие не будут затронуты)
```yaml
kubectl cordon node01
```
Вернуть ноду для возможности Schedulable
```yaml
kubectl uncordon node01
```
