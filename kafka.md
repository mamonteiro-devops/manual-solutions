

### List All Topics in a Kafka Cluster

```
kafka-topics \
--bootstrap-server localhost:9092 \
--list


kafka-topics \
--zookeeper localhost:2181 \
--list

```

### list the topics across the whole cluster, include brokers in --bootstrap-server

```
kafka-topics \
--bootstrap-server localhost:9092,localhost:9093,localhost:9094 \
--list
```


delete

```
kafka-topics \
--bootstrap-server localhost:9092,localhost:9093,localhost:9094 \
--delete \
--topic topic_for_deletion

kafka-topics \
    --bootstrap-server localhost:9092,localhost:9093,localhost:9094 
    --delete \
    --topic 'test-.*'
   
```
Create a Kafka Topic

```
kafka-topics \
--bootstrap-server localhost:9092 \
--create \
--topic topic-name
```


Create a topic with three partitions and a replication factor of 2

```
kafka-topics \
  --bootstrap-server localhost:9092 \
  --create \
  --topic topic-name \
  --partitions 3 \
  --replication-factor 2
  
```


kafka-topics \
--bootstrap-server localhost:9092 \
--describe \
--topic topic-name

### Produce Data to a Kafka Topic
```
kafka-console-producer \
--bootstrap-server localhost:9092 \
--topic topic-name
```
