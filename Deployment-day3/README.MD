# DEPLOYMENTS
- Responsável por gerenciar os Pods.
- Um Deployment é uma abstração que nos permite atualizar os Pods e também fazer o rollback para uma versão anterior caso algo dê errado.
-  possível definir o número de réplicas que queremos que ele tenha.

## Começando
1. Aplicando um deployment:
```sh
kubectl apply -f deployment.yaml
```
2. Visualizando o deployment criado:
```sh
kubectl get deployments -l app=nginx-deployment
```
3. Visualizando os pods que o deployment esta gerenciando:
```sh
kubectl get pods -l app=nginx
```
4. Visualizando os ReplicaSet que o deployment está gerenciando: 
```sh
kubectl get replicasets -l app=nginx
```
5. Visualizar detalhes do deployment:
```sh
kubectl describe deployment nginx-deployment
```

## As estratégias de atualização do Deployment
O Kubernetes possui 2 estratégias de atualização para os Deployments:
- RollingUpdate
- Recreate:

```sh
RollingUpdate: ela atualiza um Pod por vez
strategy:
    type: RollingUpdate
 ```
2. maxSurge: define a quantidade máxima de Pods que podem ser criados a mais durante a atualização
   maxUnavailable: define a quantidade máxima de Pods que podem ficar indisponíveis durante a atualização,
````sh
strategy:
  type: RollingUpdate
  rollingUpdate:
    maxSurge: 1
    maxUnavailable: 2
 ```
## Rollback: fazendo o rollback para a versão anterior do Deployment.
````sh
kubectl rollout undo deployment nginx-deployment
```
3. Historico do rollout  :
```sh
kubectl rollout history deployment nginx-deployment --revision=1
```
