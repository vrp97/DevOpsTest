# Creating Helm Chart for deploying image on Minikube


Here you will find the instruction for created Helm chart for deploying image on Minikube. At last you will get the url from where you can access the deployed helm chart on minikube.


```bash
helm install myhelmchart ./mychart/
export NODE_PORT=$(kubectl get --namespace default -o jsonpath="{.spec.ports[0].nodePort}" services mychart-service)
export NODE_IP=$(kubectl get nodes --namespace default -o jsonpath="{.items[0].status.addresses[0].address}")
echo http://$NODE_IP:$NODE_PORT
```


You can get the Pod name, namespace and status by running:

```bash
kubectl get pod -o custom-columns=POD_NAME:.metadata.name,POD_NAMESPACE:.metadata.namespace,POD_STATUS:.status.phase
```
