# Docker Kafka Config Guides
***
1. bin/zkCli.sh -server 127.0.0.1:2181 `测试server是否启动`
2. docker-compser scale my-kafka=3 `kafka集群控制`
3. ifconfig | grep "inet " `mac查看本地IP`
4. ./kafka_2.11-1.0.0/bin/kafka-topics.sh --list --zookeeper localhost:2181 `kafka topic查看`
5. ./kafka_2.11-1.0.0/bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test `创建topic`
6. ./kafka_2.11-1.0.0/bin/kafka-topics.sh --zookeeper localhost:32840 --describe --topic my-topic2 `producer 发送测试message`

7. ./kafka_2.11-1.0.0/bin/kafka-console-producer.sh --broker-list localhost:32840 --topic test ``
8. ./kafka_2.11-1.0.0/bin/kafka-console-consumer.sh --bootstrap-server localhost:32840 --from-beginning --topic test `consumer 消费数据`

# -----------explain经过测试目前还不能生效--------------
> Since Kafka 0.9.0 - it has been possible to specify multiple ports for listening on. This is to facilitate support for multiple protocols (i.e. PLAINTEXT,SASL,SSL etc) and separate internal and external traffic. With this change, host.name and port have been deprecated in favour of listeners. advertised.host.name and advertised.port have been deprecated in favour of advertised.listeners.

>Below is the same configuration represented in the deprecated and current formats:

* Deprecated

> KAFKA_HOST:
> KAFKA_PORT: 9092
> KAFKA_ADVERTISED_HOST_NAME: one.prod.com
> KAFKA_ADVERTISED_PORT: 9092

* Current
> KAFKA_LISTENERS: PLAINTEXT://:9092
> KAFKA_ADVERTISED_LISTENERS: PLAINTEXT://one.prod.com:9092
```