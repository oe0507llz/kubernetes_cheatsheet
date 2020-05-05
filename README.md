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

#### Apache Spark on Kubernetes Clusters (Anirudh Ramanathan & Sean Schter): https://www.youtube.com/watch?v=Lj-SnDqk2Ks

#### Running Spark on Kubernetes: https://spark.apache.org/docs/latest/running-on-kubernetes.html

#### SparkOperator on GKE: https://www.youtube.com/watch?v=ipejoF0okDY

#### Apache Spark on K8s - Tencent's Best Practice: https://www.youtube.com/watch?v=SqKlPiv_RRg

#### Spark on Kubernetes and related infrastructure at Lyft: https://www.youtube.com/watch?v=PPtrY_XxYBE

#### Horizontal Pod Autoscaler Walkthrough with PHP example: https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale-walkthrough/

#### HPA using Metrics Server: https://www.youtube.com/watch?v=uxuyPru3_Lc

#### Force Delete StatefulSet Pods: https://kubernetes.io/docs/tasks/run-application/force-delete-stateful-set-pod/
```
kubectl delete pods <pod>
kubectl delete pods <pod> --grace-period=0 --force
```
#### How can one create a multi-container application in helm charts: https://stackoverflow.com/questions/52634192/how-can-one-create-a-multi-container-application-in-helm-charts

#### Taints and tolerations, pod and node affinities demystified: https://banzaicloud.com/blog/k8s-taints-tolerations-affinities/

#### Taints and tolerations
https://www.youtube.com/watch?v=mo2UrkjA7FE <br>
https://kubernetes.io/docs/concepts/configuration/taint-and-toleration/

#### Kubernetes Ingress Explained Completely For Beginners
https://www.youtube.com/watch?v=GhZi4DxaxxE

#### Using NGINX as a Kubernetes Ingress Controller
https://www.youtube.com/watch?v=AXZr2OC8Unc
