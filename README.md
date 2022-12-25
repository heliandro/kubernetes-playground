# Kubernetes playground

Esse repositorio tem como proposito criar um ambiente de testes para o Kubernetes. 

# Requisitos

- Docker (https://www.docker.com/)
- Kind (https://kind.sigs.k8s.io/)
- Minikube (https://minikube.sigs.k8s.io/docs/start/)
- Kubectl (https://kubernetes.io/docs/tasks/tools/install-kubectl/)
- Helm (https://helm.sh/)
- K9s (https://k9scli.io/)

# Configuração do cluster

Cluster
- master: Control plane do Kubernetes
- node1: Node com o namespace default
- node2: Node com o namespace de desenvolvimento
- node3: Node com o namespace de producao

# Estrutura do projeto

Folders
```bash
k8s/            # Arquivos de configuracao do Kubernetes
  vanilla/      # Manifestos k8s para deploy de aplicacoes e servicos - vanilla k8s way
  charts/       # Helm charts para deploy de aplicacoes e servicos - best way
```
# Setup do cluster

Podemos fazer o setup usando Kind ou Minikube, escolha o que melhor se encaixa no seu ambiente.

## Kind

```bash
kind create cluster --name kind-helios --config k8s/kind/kind-cluster.yaml
```

## Minikube

```bash
minikube start --nodes 4 -p minikube-helios --kubernetes-version=latest --cpus 2 --memory 2048 --disk-size 20g
```
