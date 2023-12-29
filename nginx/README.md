# Project Name

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

## Usage



## Contributing

Guidelines on how to contribute to the project.

## License

Information about the project's license.
