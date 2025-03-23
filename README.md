# quant_flow

# Airflow through k8s
```
helm install airflow apache-airflow/airflow \
  -n airflow --create-namespace \
  -f airflow/k8s/values.yaml
  
# background
nohup kubectl port-forward svc/airflow-webserver 8080:8080 -n airflow
```
