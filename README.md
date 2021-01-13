# Kafka

1. Apache Kafka® is an `event streaming platform`.

   - To `publish (write)` and `subscribe to (read)` streams of events, including continuous import/export of your data from other systems.
   - To `store streams` of events durably and reliably for as long as you want.
   - To `process streams` of events as they occur or retrospectively.

2. Kafka is a` distributed system consisting of servers and clients`.

   - ## Servers:

     - Kafka is run as a `cluster of one or more servers` that can span multiple datacenters or cloud regions.
     - Some of these servers form the storage layer, `called the brokers`.
     - Other servers run Kafka Connect to continuously import and export data as event streams to integrate Kafka with your existing systems such as relational databases as well as other Kafka clusters.

   - ## Clients:
     - They `allow you to write distributed applications and microservices that read, write, and process streams of events in parallel`, at scale, and in a fault-tolerant manner even in the case of network problems or machine failures.
     - Kafka ships with some such clients included, which are augmented by dozens of clients provided by the Kafka community: clients are `available for Java and Scala`

## KAFKA CORE CONCEPTS

1. **PRODUCER**

   - It is the `application which send messages or publish (write) events to kafka sercer/broker`.
   -

2. **CONSUMER**:-

   - It is the `application which reads message from kafka server/broker`
   - consumers are those `that subscribe to (read and process) these events`.

3. **KAFKA SERVER / BROKER**

   - A Kafka broker is known as KafkaServer that` hosts topics`.
   - A Kafka broker `receives messages from producers and stores them on disk keyed by unique offset`.
   - A Kafka broker `allows consumers to fetch messages by topic, partition and offset`.
   - Kafka brokers can c`reate a Kafka cluster by sharing information between each other directly or indirectly using Zookeeper`.

4. **Kafka Broker**

   - A Kafka cluster consists of `one or more servers (Kafka brokers) running Kafka`.
   - Producers are processes that push records into Kafka topics within the broker.
   - A consumer pulls records off a Kafka topic.

5. **Kafka Topic**

   - A Topic is a `unique category/feed name to which records` are stored and published.

6. **Kafka topic partition**

   - Topics can be` divided into partition to store in kafka server` as on topic can be huge in size.
   - Its the `responsibility of our to decide the no of partition` as each partition sits in one computer.
   - Kafka topics are divided into a number of partitions, which contain records in an unchangeable sequence. Each record in a partition is assigned and identified by its unique offset.

7. **OFFSET**

   - it is `the sequenceId given to the messages as they arrive in the partition`.
   - consumers responsible for tracking the position in the log, known as the “offset”.

8. **Consumer Group**
   - A `group of consumer acting as a single logical unit`.
   - **maximum no consumer can be in a `group <= no of partition` in a kafka server** to avoid reading of same data broker doesnot allow more than one consumer to read from same partition.
   - Here a consumer group is `created by adding the property “group.id” to a consumer`. Giving the same group id to another consumer means it will join the same group.
   - Every time a `consumer is added or removed from a group the consumption is rebalanced between the group`. All consumers are stopped on every rebalance, so clients that time out or are restarted often will decrease the throughput. `Make the consumers stateless since the consumer might get different partitions assigned on a rebalance`.
   - The number of partitions impacts the maximum parallelism of consumers as there cannot be more consumers than partitions.
   - Records are never pushed out to consumers, `the consumer will ask for messages when the consumer is ready to handle the message`.

## to locate a message one should have:-

```
    Topic   ----->       Partition       ----->        Offset
```
