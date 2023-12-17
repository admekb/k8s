Сделать ноду noSchedulable и выселить все поды
```yaml
kubectl drain node01 --ignore-daemonsets
```
Вернуть ноду для возможности Schedulable
```yaml
kubectl uncordon node01
```
