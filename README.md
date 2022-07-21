# CAPI-K8sCD
Mimics a Production SDLC with Kubernetes and ArgoCD in your local machine using Docker.

Prerequisites

* Docker
* kind
* clusterctl
* kubectl

Create a Management Cluster in Kind with the following command.
```sh
kind create cluster --config management/mgmt-cluster.yaml --name mgmt
```

Then init the CAPI management cluster by targetting the recently created mgmt kind cluster.

```sh
clusterctl init --infrastructure docker
```

```sh
kubectl apply -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```