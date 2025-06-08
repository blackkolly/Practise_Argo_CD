# Practise_Argo_CD
# Argo CD Hands-On Lab 🚀

A practical guide to learning **Argo CD**, the declarative GitOps tool for Kubernetes. This repo includes setup instructions, example apps, and advanced workflows to master continuous delivery with Argo CD.It enables to uunderstand the 

---

## 🏁 Quick Start

### Prerequisites
- Kubernetes cluster ([Minikube](https://minikube.sigs.k8s.io/docs/start/), [Kind](https://kind.sigs.k8s.io/), or cloud provider)
- `kubectl` configured
- Argo CD CLI (`argocd`) (optional)

### 1. Install Argo CD
```bash
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

2. Access the Argo CD UI
bash

kubectl port-forward svc/argocd-server -n argocd 8080:443

    URL: https://localhost:8080

    Username: admin

    Password: Retrieve with:
    bash

    kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
Deploy Your First App
bash

argocd app create guestbook \
  --repo https://github.com/argoproj/argocd-example-apps.git \
  --path kustomize-guestbook \
  --dest-namespace default

