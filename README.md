

##Namespace
Все действия будем выполнять в namespace "vk"
```bash
  kubectl create namespace vk
```
# Для разворачивания веб-приложения будем идти по следующим шагам:
##1.ConfigMap
```bash
  kubectl apply -f nginx-configmap.yaml
```
##2.Deployment
```bash
  kubectl apply -f nginx-deployment.yaml
```
##3.Service
```bash
  kubectl apply -f nginx-service.yaml
```
##4.Установка Ingress Nginx контроллера
```bash
  helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
  helm repo update
  helm install ingress-nginx ingress-nginx/ingress-nginx --namespace vk
```
##5.Создание Ingress
```bash
  kubectl apply -f nginx-ingress.yaml
```
## Логи:
```bash
  kubectl get pods -n vk
  kubectl get svc -n vk
  kubectl get ingress -n vk
```
