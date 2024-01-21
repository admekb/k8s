Проверить разрешен ли доступ пользователю
```console
kubectl auth can-i create deployments
```
```console
kubectl auth can-i delete nodes
```
```console
kubectl auth can-i create deployments --as dev-user
```
