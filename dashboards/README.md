## Install, configure and start Kibana

### Manual installation

Download Kibana from https://www.elastic.co/fr/downloads/kibana

Set Kibana base path and index name in config/kibana.yml:

```
server.basePath: "/<webappname>/dashboard"

kibana.index: ".dashboards"

```

Start Kibana manually:

```
cd kibana/bin
./kibana
```

Import configuration:

```
curl -X PUT http://localhost:9200/.dashboards/index-pattern/indicators -d @config/idx-pattern-indicators.json
curl -X PUT http://localhost:9200/.dashboards/index-pattern/records -d @config/idx-pattern-records.json




## TODO: Fix to load using bulk mode
curl -X PUT http://localhost:9200/.dashboards -d @config/dashboards.json
```


### Maven installation

Maven could take care of the installation steps:
* download
* initialize collection
* start

Use the following commands:

```
cd dashboards
mvn install -Pkb-download
mvn exec:exec -Dkb-start
```

### Production use

Configure Kibana to start on server startup.


