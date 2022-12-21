# Kubernetes playground

Esse repositorio tem como proposito criar um ambiente de testes para o Kubernetes. O ambiente é composto por 4 conteineres, sendo uma para o master e tres para os nodes.

# Requisitos

- Docker (https://www.docker.com/)
- Kind (https://kind.sigs.k8s.io/)
- Kubectl (https://kubernetes.io/docs/tasks/tools/install-kubectl/)
- Helm (https://helm.sh/)
- K9s (https://k9scli.io/)

# Estrutura

Cluster
- master: Control plane do Kubernetes
- node1: Node com o namespace default
- node2: Node com o namespace de desenvolvimento
- node3: Node com o namespace de producao

Folders
```bash
k8s/            # Arquivos de configuracao do Kubernetes
  apps/         # Arquivos de configuracao dos aplicativos
  services/     # Arquivos de configuracao dos servicos
charts/         # Arquivos de configuracao do Helm, para deploy de aplicacoes
```
# Instalacao

```bash
kind create cluster --name helios --config k8s/kind/kind-cluster.yaml
```
