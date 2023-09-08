# Kubernets

You should create a kubernetes cluster using tools like Minikube, K3s, Kind, etc, and apply nginx ingress controller to manage inbound HTTP traffic.

## Applying K8S objects

Replace the `<DOMAIN_NAME>` on `./ingress-nginx/ingress.yml` and run the follow command for create deployment, service and ingress rules.

```sh
kubectl apply -f ingress-nginx/
```

## Getting nginx ingress controller service IP

Getting the EXTERNAL-IP of `ingress-nginx-controller`.

```sh
kubectl get service -n ingress-nginx
```

Adding your domain to resolve local hosts.

```sh
echo <DOMAIN_NAME> <INGRESS_EXTERNAL_IP> >> /etc/hosts
```

## Access ingress controller from local machine

Now you can access the ingress controller from your local machine using curl or through browser.

```sh
curl http://<DOMAIN_NAME>
```
