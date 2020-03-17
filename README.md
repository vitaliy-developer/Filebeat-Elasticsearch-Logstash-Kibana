helm dependency update elastic-stack-ELK/ 
helm install --name elk elastic-stack-ELK/
helm install --name filebeat filebeat/
kubectl port-forward svc/elk-elasticsearch-client 9200:9200
curl http://localhost:9200/_aliases?pretty=true
curl -XGET 'localhost:9200/filebeat-2020.03.16/_search'
kubectl port-forward elk-kibana-6fc998c7b5-8xdjg 5601
open browser http://127.0.0.1:5601/
