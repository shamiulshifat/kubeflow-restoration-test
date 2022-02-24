## After backup of k8s cluster, k8s is running but kubeflow will throw errors.

So remove kubeflow first
```
microk8s disable kubeflow
````

Then install juju:

https://juju.is/docs/olm/microk8s

Then add a juju model kubeflow and follow the process to deploy kubeflow:

https://charmed-kubeflow.io/docs/quickstart


***************************
Finding the URL: If you have a different setup for microk8s, or you are adapting this tutorial for a different Kubernetes, 
you can find the URL required by examining the IP address of the istio-ingressgateway service. 

For example, you can determinine this information using kubectl :
```
microk8s kubectl -n kubeflow get svc istio-ingressgateway -o jsonpath='{.status.loadBalancer.ingress[0].ip}'
```
**************************************
