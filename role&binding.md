Проверить разрешен ли доступ пользователю
```console
kubectl auth can-i create deployments
```
```console
kubectl auth can-i delete nodes --namespace test
```
```console
kubectl auth can-i create deployments --as dev-user
```
