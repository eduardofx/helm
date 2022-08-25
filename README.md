Helm

Package: https://artifacthub.io

List repository

> helm repo list

Add repository

> helm repo add bitnami https://charts.bitnami.com/bitnami


update charts

> helm repo update

remove repository

> helm repo remove bitnami


List kubernetes resources
> kubectl get all

Wait pod UP
> kubectl get pods -w

Port Redirect
> kubectl port-forward --namespace default svc/my-release-phpmyadmin 8080:80
