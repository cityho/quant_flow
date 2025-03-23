# airflow debug for k8s

1. initialize helm install
```
# uninstall existing installed resource
helm uninstall airflow -n airflow
kubectl delete pvc -l app.kubernetes.io/instance=airflow -n airflow
docker image rm apache/airflow:2.8.1

# re-install
helm install airflow apache-airflow/airflow \
  -n airflow --create-namespace \
  -f airflow/k8s/values.yaml \
  --timeout 10m
```