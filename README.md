# BDE SC4 Pilot Pipeline

Bootstrap the pipeline for the SC4 pilot on the BDE platform.

## Pilot Description
The pilot fetches continuously data about taxies in Thessaloniki from CERTH web service. A Kafka Producer connects 
to the web service and sends the data into a Kafka topic. The data is consumed by a Flink job, enriched using a map
matching algorithm and aggregated and finally stored into Elasticsearch. A visualization based on Kibana is used to visualize the data in a map.
  
## Pilot Components
The table shows the frameworks and other components used to set up the pilot.

|Component | Images |
|----------|--------|
|Apache Kafka|[bde2020/docker-kafka](https://hub.docker.com/r/bde2020/docker-kafka/)|
|FCD Kafka Producer|Dockerized version of [pilot-sc4-kafka-producer](https://github.com/big-data-europe/pilot-sc4-kafka-producer) (TBD)|
|Apache Flink|[bde2020/flink-master](https://hub.docker.com/r/bde2020/docker-kafka/) <br> [bde2020/flink-worker](https://hub.docker.com/r/bde2020/flink-worker/) <br> [bde2020/flink-submit](https://hub.docker.com/r/bde2020/flink-worker/)|
|Elasticsearch|NA|
|Rserve + MapMatching Algorithm|Dockerfile in [pilot-sc4-docker-r](https://github.com/big-data-europe/pilot-sc4-docker-r)|
|FCD Flink Job|Dockrized version of [pilot-sc4-flink-kafka-consumer](https://github.com/big-data-europe/pilot-sc4-flink-kafka-consumer) (TBD)|
|Kibana|NA|

## Pilot Initialization
Some of the components used for the pilot depend on other components. As an example, the Kafka producer depends on 
the availability of a Kafka topic, the Flink job depends on the availability of the Rserve for the map matching and 
on Elasticsearch for the storage. Kafka itself depends on Zookeeper. The BDE platform provides a component, the 
[init daemon service](https://github.com/big-data-europe/mu-init-daemon-service) to execute a proper initialization.
The init daemon is already include in the docker-compose.yml file used for the pilot. The init daemon requires the 
information about the order in which the components have to be started. This information must be provided as an RDF 
file that can be created using the [Pipeline Builder](https://github.com/big-data-europe/app-pipeline-builder). The
RDF file must be included in the project as it will be imported by the initialization daemon.  

## Running the pilot
```
git clone https://github.com/big-data-europe/pilot-sc4-pipeline.git
cd pilot-sc4-pipeline
docker-compose up -d
```
