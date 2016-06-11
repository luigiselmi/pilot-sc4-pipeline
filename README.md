# BDE SC4 Pilot Pipeline

Bootstrap the pipeline for the SC4 pilot on the BDE platform.

## Pilot Components
The table shows the frameworks and other components used to set up the pilot.

|Component | Images |
|----------|--------|
|Apache Kafka|[bde2020/docker-kafka](https://hub.docker.com/r/bde2020/docker-kafka/)|
|Apache Flink|[bde2020/flink-master](https://hub.docker.com/r/bde2020/docker-kafka/) \
              [bde2020/flink-worker](https://hub.docker.com/r/bde2020/flink-worker/)|

## Running the application
```
git clone https://github.com/big-data-europe/pilot-sc4-pipeline.git
cd pilot-sc4-pipeline
docker-compose up -d
```
