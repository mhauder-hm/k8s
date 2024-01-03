This i# Project Name

A brief description of the project.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Installation

1. Launch minikube with Docker Desktop started. 

    `minikube start --driver=docker`

2. Create namespace for ArgoCD

    `kubectl create ns argocd`

3. Apply ArgoCD manifest

    `kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/v2.5.8/manifests/install.yaml`

4. Verify installation with all objects running

    `kubectl get all -n argocd`

5. Prepare ArgoCD user interface on localhost:8080

    `kubectl port-forward svc/argocd-server -n argocd 8080:443`

6. Use login admin and retrieve password for ArgoCD (example for linux)

    `kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo`

7. Connect this repository in ArgoCD for a new application

### Problems 

## Usage

1. Postgres has a kubernetes secret for the initial deployment. If helm chart in uninstalled, then the PVC and the PV need to be deleted manually.

2. pgAdmin: PS D:\Code\k8s> helm install my-release runix/pgadmin4
>>
NAME: my-release
LAST DEPLOYED: Wed Jan  3 18:16:40 2024
NAMESPACE: default
STATUS: deployed
REVISION: 1
NOTES:
1. Get the application URL by running these commands:
  export POD_NAME=$(kubectl get pods --namespace default -l "app.kubernetes.io/name=pgadmin4,app.kubernetes.io/instance=my-release" -o jsonpath="{.items[0].metadata.name}")
  echo "Visit http://127.0.0.1:8080 to use your application"
  kubectl port-forward $POD_NAME 8080:80

## Contributing

Guidelines on how to contribute to the project.

## License

Information about the project's license.
s a simple nginx application to demonstarte working with argocd.
