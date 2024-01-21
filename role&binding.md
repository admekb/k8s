Изменить роль
```console
kubectl edit role developer -n blue
```
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

Пример создания Role
```console
kubectl create role developer --namespace=default --verb=list,create,delete --resource=pods
```

```yaml
kind: Role
apiVersion: rbac.authorization.k8s.io/v1
metadata:
  namespace: default
  name: developer
rules:
- apiGroups: [""]
  resources: ["pods"]
  verbs: ["list", "create","delete"]
- apiGroups:
  - apps
  resources:
  - deployments
  verbs:
  - create
```
```console
kubectl create rolebinding dev-user-binding --namespace=default --role=developer --user=dev-user
```
Пример создания RoleBinding
```yaml
kind: RoleBinding
apiVersion: rbac.authorization.k8s.io/v1
metadata:
  name: dev-user-binding
subjects:
- kind: User
  name: dev-user
  apiGroup: rbac.authorization.k8s.io
roleRef:
  kind: Role
  name: developer
  apiGroup: rbac.authorization.k8s.io
```
