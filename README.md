# Jenkins en Kubernetes

Desplegar automáticamente un servidor Jenkins en Kubernetes.

## Puesta en marcha

```
kubectl apply -f https://raw.githubusercontent.com/egibide-ciberseguridad/jenkins-kubernetes/main/namespace.yaml
kubectl apply -n devops-tools -f https://raw.githubusercontent.com/egibide-ciberseguridad/jenkins-kubernetes/main/serviceAccount.yaml
kubectl apply -n devops-tools -f https://raw.githubusercontent.com/egibide-ciberseguridad/jenkins-kubernetes/main/deployment.yaml
kubectl apply -n devops-tools -f https://raw.githubusercontent.com/egibide-ciberseguridad/jenkins-kubernetes/main/volume.yaml
kubectl apply -n devops-tools -f https://raw.githubusercontent.com/egibide-ciberseguridad/jenkins-kubernetes/main/service.yaml
kubectl apply -n devops-tools -f https://raw.githubusercontent.com/egibide-ciberseguridad/jenkins-kubernetes/main/ingress.yaml
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
- [Rook Storage Architecture](https://rook.io/docs/rook/latest-release/Getting-Started/storage-architecture/)
