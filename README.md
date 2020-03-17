1. helm dependency update elastic-stack-ELK/ 
2. helm install --name elk elastic-stack-ELK/
3. helm install --name filebeat filebeat/
4. kubectl port-forward svc/elk-elasticsearch-client 9200:9200
5. curl http://localhost:9200/_aliases?pretty=true
6. curl -XGET 'localhost:9200/filebeat-2020.03.16/_search'
7. kubectl port-forward elk-kibana-6fc998c7b5-8xdjg 5601
8. open browser http://127.0.0.1:5601/
