# Concepts
1. Append only "log" data structure is the building block for data stored within kafka topic
2. For horizontal scaling
    1. Topic is paritioned/stored across multiple brokers within a cluster
    2. Given partition data is always consumed once by one of the consumer of a consumer group.
    3. However, single consumer can be assigned to handle multiple partitions
3. Default no. of partitions for a topic is 1(server default)
    1. per topic config can be overriden - Refer here(https://kafka.apache.org/documentation/#topicconfigs)
4. For fault tolerance - data in a partition is replicated across brokers via topic replication factor.
5. Producers and consumers connect to broker over TCP and use custom kakfa protcol to communicate
6. Ordering of events is guaranteed within a single topic partition.
7. Kafka KRaft consensus algo. repartitions the partitons as we add/remove consumers in a consumer group

# Project Setup 
1. For staging and local env. setup - use docker-compose with yml config. and zookeeper and kafka service. Refer https://www.baeldung.com/ops/kafka-new-topic-docker-compose
2. While modelling unique messages to different kafka topics, ensure no ordering issues due to parallel  out of order consumption of messages around same entity for eg. customer via different consumers.
3. JSON based message payload with statically defined schema which is version controlled in git using java classes. We didn't had schema registry setup. Refer https://www.linkedin.com/pulse/kafka-schema-registry-zhiqiang-tang/
   
## Evolving Topic message schemas in the running production cluster



# Intro to Kafka
https://2minutestreaming.beehiiv.com/p/summary-introduction-apache-kafka

# Kafka-consumer-group-basics
https://2minutestreaming.beehiiv.com/p/kafka-consumer-group-basics

# Tiered Storage
https://2minutestreaming.beehiiv.com/p/apache-kafka-kip-405-tiered-storage
