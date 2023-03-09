# Kubernetes Manifests for Jenkins Deployment

Refer https://devopscube.com/setup-jenkins-on-kubernetes-cluster/ for step by step process to use these manifests.

## Puesta en marcha

```
kubectl apply -f https://raw.githubusercontent.com/egibide-ciberseguridad/kubernetes-jenkins/main/namespace.yaml
kubectl apply -f https://raw.githubusercontent.com/egibide-ciberseguridad/kubernetes-jenkins/main/serviceAccount.yaml
kubectl apply -f https://raw.githubusercontent.com/egibide-ciberseguridad/kubernetes-jenkins/main/deployment.yaml
kubectl apply -f https://raw.githubusercontent.com/egibide-ciberseguridad/kubernetes-jenkins/main/volume.yaml
kubectl apply -f https://raw.githubusercontent.com/egibide-ciberseguridad/kubernetes-jenkins/main/service.yaml
```

## Referencias

-[Setup Jenkins On Kubernetes](https://www.jenkins.io/doc/book/installing/kubernetes/)
