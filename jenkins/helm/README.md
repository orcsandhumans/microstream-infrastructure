

```bash

helm install jenkins stable/jenkins -f values.yaml


helm repo add jenkins https://charts.jenkins.io
helm repo update

helm install jenkins -n jenkins jenkinsci/jenkins -f jenkins-values.yaml
helm uninstall jenkins

#helm install jenkins -n jenkins --create-namespace -f jenkins-values.yaml jenkinsci/jenkins
#helm uninstall jenkins -n jenkins
```



### Debugging
```bash
kubectl logs -n jenkins pod/jenkins-0
kubectl logs -n jenkins -l app.kubernetes.io/name=jenkins -c jenkins
kubectl describe pod jenkins-0 -n jenkins
kubectl get pvc -n jenkins
kubectl describe pvc -n jenkins
```

```bash
kubectl port-forward -n jenkins svc/jenkins 8080:8080
```


> [!note]
> check `kubectl get storageclass` before installing jenkins on a cloud.

### Steps to Retrieve Jenkins Admin Password:
1. Get the Secret Name for Jenkins Password: `kubectl get secrets -n jenkins`
2. Retrieve the Password from the Secret: 
```bash
kubectl get secret sh.helm.release.v1.jenkins.v1 -n jenkins -o jsonpath='{.data.jenkins-admin-password}' | base64 --decode
```

## Secrets
### How to describe secrets
```bash
kubectl describe secret sh.helm.release.v1.jenkins.v1 -n jenkins
```
### How to create secrets
```bash
kubectl create secret generic secret-credentials --from-literal=github-token=<token>
```

### Local installation
```bash
kubectl apply -f jenkins-pv.yaml -n jenkins
kubectl apply -f jenkins-pvc.yaml -n jenkins
helm install jenkins -n jenkins jenkinsci/jenkins -f jenkins-values.yaml

kubectl delete pv jenkins-pv
kubectl delete pvc jenkins-pvc -n jenkins
helm uninstall jenkins -n jenkins
```