# Jenkins en Kubernetes

Desplegar automáticamente un servidor Jenkins en Kubernetes.

## Puesta en marcha

```
kubectl apply -f https://raw.githubusercontent.com/egibide-ciberseguridad/jenkins-kubernetes/main/namespace.yaml
kubectl apply -f https://raw.githubusercontent.com/egibide-ciberseguridad/jenkins-kubernetes/main/serviceAccount.yaml
kubectl apply -f https://raw.githubusercontent.com/egibide-ciberseguridad/jenkins-kubernetes/main/deployment.yaml
kubectl apply -f https://raw.githubusercontent.com/egibide-ciberseguridad/jenkins-kubernetes/main/volume.yaml
kubectl apply -f https://raw.githubusercontent.com/egibide-ciberseguridad/jenkins-kubernetes/main/service.yaml
```

## Obtener el token de acceso inicial

```
kubectl -n devops-tools exec deployment/jenkins -- cat /var/jenkins_home/secrets/initialAdminPassword
```

## Borrar todo el despliegue

```
kubectl delete namespace devops-tools
```

## Referencias

- [Tutorial original](https://devopscube.com/setup-jenkins-on-kubernetes-cluster/)
- [Setup Jenkins On Kubernetes](https://www.jenkins.io/doc/book/installing/kubernetes/)
- [Use HAProxy Kubernetes Ingress Controller to terminate SSL / TLS](https://www.haproxy.com/documentation/kubernetes/latest/usage/terminate-ssl/)
- [Enable TLS with Let’s Encrypt and the HAProxy Kubernetes Ingress Controller](https://www.haproxy.com/blog/enable-tls-with-lets-encrypt-and-the-haproxy-kubernetes-ingress-controller/)
- [cert-manager](https://github.com/cert-manager/cert-manager)
- [Securing Ingress Resources](https://cert-manager.io/docs/usage/ingress/)
- [Configuring the HTTP01 Ingress solver](https://cert-manager.io/docs/configuration/acme/http01/#configuring-the-http01-ingress-solver)
- [Troubleshooting](https://cert-manager.io/docs/troubleshooting/)
- [Allowing skipping HTTP01 and DNS01 self-check on a per-solver basis](https://github.com/cert-manager/cert-manager/issues/1292)
- [hairpin-proxy](https://github.com/compumike/hairpin-proxy)
- [Rate Limits](https://letsencrypt.org/docs/rate-limits/)
- [Staging Environment](https://letsencrypt.org/docs/staging-environment/)
- [Rook Storage Architecture](https://rook.io/docs/rook/latest-release/Getting-Started/storage-architecture/)
