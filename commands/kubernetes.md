Kubernetes commands


List kubernetes resources

> kubectl get all

Wait pod UP

> kubectl get pods -w

Port Redirect

> kubectl port-forward --namespace default svc/my-release-phpmyadmin 8080:80
