## Install, configure and start Elasticsearch

### Manual installation

Download Elasticsearch from https://www.elastic.co/fr/downloads/elasticsearch
and copy it to the ES module. eg. es/elasticsearch-5.2.1

Start ES.

Configure index
```
curl -X PUT http://localhost:9200/records -d @config/records.json
```

### Maven installation

Maven could take care of the installation steps:
* download
* initialize collection
* start

Use the following commands:

```
cd es
mvn install -Pes-download
mvn exec:exec -Des-start
curl -X PUT http://localhost:9200/records -d @config/records.json
curl -X PUT http://localhost:9200/indicators -d @config/indicators.json
```

### Production use

Configure ES to start on server startup.


### Updating a collection


TODO
