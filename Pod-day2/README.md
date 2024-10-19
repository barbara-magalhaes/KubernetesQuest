# PODS
É  a menor unidade do kuberntes, uma caixinha que contém um ou vários conteiners.
- compartilham IP, namespace, volumes etc...

## Começando
1. criando um pod por comando no terminal ou por arquivo YAML.
```sh
kubectl run giropops --image=nginx --port=80
```
2. Visualizando o pod criado/execucao:
```sh
kubectlget pods
kubectl get pods --all-namespaces
kubectl get pods -A
```
3. Visualizando pods de um namespace especifico:
```sh
kubectl get pods -n <namespace>
```
4. Ver detalhes sobre o pod:
```kubectl describe pods giropops
```
## Criando pod com yaml :
```sh
kubectl apply -f pod.yaml
kubectl logs -f giropops
 ```
2. Deletar
````sh
 kubectl delete pods giropops
 ```
## Pods com mais de um container:
```kubectl exec giropops -c strigus -- ls     #executando comandos      
```
3. se conectar dentro em um pod :
```sh
kubectl attach giropops -c strigus
```
