# Introduction
This project shows how a developer/architect can protect his application using Oauth2 proxy.

Oauth2 proxy is a reverse proxy that that provides authentication using Providers (Google, GitHub, and others) to validate accounts by email, domain or group.

I will show tree kind of integrations:
- Pod as reverse proxy
- Sidecar container
- Nginx Ingress controller plugin


# Pod as reverse proxy
cd pod
NS=lab
kubectl create ns $NS
kubectl apply -f application.yaml -n $NS
kubectl port-forward svc/starevent-frontend 8080:8080 -n $NS

kubectl apply -f oauth2proxy.yaml -n $NS

kubectl port-forward svc/starevent-frontend 8080:8080 -n $NS

kubectl delete ns $NS

# Sidecar container



# Nginx Ingress controller plugin