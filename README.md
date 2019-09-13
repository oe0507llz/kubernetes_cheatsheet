# kubernetes_cheatsheet

#### Installing Helm in Google Kubernetes Engine (GKE)
https://medium.com/google-cloud/installing-helm-in-google-kubernetes-engine-7f07f43c536e
```
git clone https://github.com/jonbcampos/kubernetes-series.git
cd ~/kubernetes-series/helm/scripts
sh startup.sh
sh add_helm.sh
helm install --name my-release stable/spark
kubectl get pods
kubectl exec -it my-release-master-74c54fc456-45lm6 /bin/bash
spark-submit --class org.apache.spark.examples.SparkPi --master spark://my-release-master:7077 spark-example.jar 10
sh teardown.sh
```
https://github.com/helm/charts/tree/master/stable/spark

#### Kubernetes Tips: Using a ServiceAccount: https://medium.com/better-programming/k8s-tips-using-a-serviceaccount-801c433d0023

#### The Kubernetes API call is coming from inside the cluster: https://medium.com/@pczarkowski/the-kubernetes-api-call-is-coming-from-inside-the-cluster-f1a115bd2066
```
/ # K8S=https://$KUBERNETES_SERVICE_HOST:$KUBERNETES_SERVICE_PORT
/ # TOKEN=$(cat /var/run/secrets/kubernetes.io/serviceaccount/token)
/ # CACERT=/var/run/secrets/kubernetes.io/serviceaccount/ca.crt
/ # NAMESPACE=$(cat /var/run/secrets/kubernetes.io/serviceaccount/namespace)
/ # curl -H "Authorization: Bearer $TOKEN" --cacert $CACERT $K8S/healthz
ok
```
#### Effective RBAC - Jordan Liggitt, Red Hat: https://www.youtube.com/watch?v=Nw1ymxcLIDI
