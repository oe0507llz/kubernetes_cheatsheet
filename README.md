# kubernetes_cheatsheet

#### Installing Helm in Google Kubernetes Engine (GKE)
https://medium.com/google-cloud/installing-helm-in-google-kubernetes-engine-7f07f43c536e
```
git clone https://github.com/jonbcampos/kubernetes-series.git
cd ~/kubernetes-series/helm/scripts
sh startup.sh
sh add_helm.sh
helm install --name my-release stable/spark
```
https://github.com/helm/charts/tree/master/stable/spark
