Сделать ноду noShedule и выселить все поды
```yaml
kubectl drain node01 --ignore-daemonsets
```
Вернуть ноду для возможности деплоя
```yaml
kubectl uncordon node01
```
