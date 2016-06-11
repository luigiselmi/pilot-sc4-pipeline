# BDE SC4 Pilot Pipeline

Bootstrap the pipeline for the SC4 pilot on the BDE platform.

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

## Running the pilot
```
git clone https://github.com/big-data-europe/pilot-sc4-pipeline.git
cd pilot-sc4-pipeline
docker-compose up -d
```
