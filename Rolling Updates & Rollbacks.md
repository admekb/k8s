Существует две Deployment Strategy:
Recreate - полная остановка pod со старой версией и поднятие новых с новой версией
<img width="1382" alt="Снимок экрана 2023-12-17 в 22 05 06" src="https://github.com/admekb/k8s/assets/65552449/91952317-3057-4db3-934c-7b6c40a159af">
Rolling Update - постепенная остановка pod (задается в процентах) со старой версией и поднятие с новой версией (задается в процентах)
<img width="1388" alt="Снимок экрана 2023-12-17 в 22 05 46" src="https://github.com/admekb/k8s/assets/65552449/efaceb39-03e5-4412-8634-0e470d05f367">
Создать деплоймент:
```yaml
kubectl create –f deployment-definition.yml
```
Посмотреть деплоймент:
```yaml
kubectl get deployments
```
Создать/изменить деплоймент:
```yaml
kubectl apply –f deployment-definition.yml
```
Изменить образ в деплоймент:
```yaml
kubectl set image deployment/myapp-deployment nginx=nginx:1.9.1
```
Посмотреть статус пересоздания pod на новую версию в деплоймент:
```yaml
kubectl rollout status deployment/myapp-deployment
```
Посмотреть историю изменений в деплоймент:
```yaml
kubectl rollout history deployment/myapp-deployment
```
Откатить деплоймент:
```yaml
kubectl rollout undo deployment/myapp-deployment
```
Быстрый запуск деплоймент:
```yaml
kubectl run nginx --image=nginx
```
