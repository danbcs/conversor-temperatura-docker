# Projeto conversão de temperatura

### Sobre o projeto
O projeto conversão de temperatura é um projeto desenvolvido em NodeJS. O projeto tem como objetivo ser um exemplo para a criação de ambiente com containers usando NodeJS.

### Observações do projeto
A aplicação é exposta usando a porta 8080

### Imagem e Container Docker
Imagem criada via Dockerfile, com Imagem origem node:alpine

Criar Imagem:
```
docker build -t user/conversao-temperatura:v1 .
```

Publicar Imagem:
```
docker push user/conversao-temperatura:v1
```

Executar Container:
```
docker container run -d -p 8080:8080 user/conversao-temperatura:v1
```
### Orquestrador de Container - Kubernetes

Criar orquestrador com K3D:
```
k3d cluster create -p 81:30000 cluster-temp
```
Rodar deployment k8s:
```
kubectl apply -f deployment.yaml
```
Acessar aplicação por:
```
localhost:81
```

### Comandos importantes
```
k3d cluster delete nome-cluster
kubectl get all
kubectl get po
kubectl get svc
kubectl describe
```