## Типы шифрования
* SYMMETRIC ENCRYPTION - шифрование в котом ключ которым зашифровали сообщение передается получателю для расшифрки сообщения (может быть перехвачен хакером)
* ASYMMETRIC ENCRYPTION - шифрование в котом используется pair keys а именно private key и public key ( один с помошью другого может как зашифровать так и расшифровать данные)

Посмотреть информацию о сертификате:
```console
openssl x509 -in /etc/kubernetes/pki/apiserver.crt -text -noout
```
Зашифровать сертификат:
```console
cat akshay.csr | base64 -w 0
```
Запрос на подпись сертификата
```yaml
---
apiVersion: certificates.k8s.io/v1
kind: CertificateSigningRequest
metadata:
  name: akshay
spec:
  groups:
  - system:authenticated
  request: <Paste the base64 encoded value of the CSR file>
  signerName: kubernetes.io/kube-apiserver-client
  usages:
  - client auth
```
Посмотреть запросы на подпись сертификата
```console
kubectl get csr
```
Апрвунуть запрос на подпись сертификата
```console
kubectl certificate approve akshay
```
Отклонить запрос на подпись сертификата
```console
kubectl certificate deny agent-smith
```
Удалить сертификат на подпись
```console
kubectl delete csr agent-smith
```
