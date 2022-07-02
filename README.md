# Logging

> for logging we use ELK+F stack 
> since logs from pods that are maintained by argocd can be seen using argocd UI, we only store airflow logs here

## Installation 
```bash 
helm repo add elastic https://helm.elastic.co
helm repo update

helm install elastic  -n logging --create-namespace elastic/elasticsearch -f elasticsearch/values.yaml
helm install kibana   -n logging --create-namespace elastic/kibana        -f kibana/values.yaml
helm install filebeat -n logging --create-namespace elastic/filebeat      -f filebeat/values.yaml
helm install logstash -n logging --create-namespace elastic/logstash      -f logstash/values.yaml

```


