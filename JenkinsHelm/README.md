# Jenkins chart on Minikubw


Here you will find the instruction for getting public helm chart to Deploy jenkins chart on Minikube.


```bash
helm repo add jenkins https://charts.jenkins.io
helm repo update
minikube start
helm install jenkins-helm-k8s jenkins/jenkins
```

1. Get your 'admin' user password by running:
```bash
printf $(kubectl get secret --namespace default jenkins-helm-k8s -o jsonpath="{.data.jenkins-admin-password}" | base64 --decode);echo
```

2. Get the Jenkins URL to visit by running these commands in the same shell:
```bash
export POD_NAME=$(kubectl get pods --namespace default -l "app.kubernetes.io/component=jenkins-master" -l "app.kubernetes.io/instance=jenkins-helm-k8s" -o jsonpath="{.items[0].metadata.name}")
echo http://127.0.0.1:8080
kubectl --namespace default port-forward $POD_NAME 8080:8080
```

3. Login with the password from step 1 and the username: admin


Referred from [Here](https://artifacthub.io/packages/helm/jenkinsci/jenkins#jenkins)
