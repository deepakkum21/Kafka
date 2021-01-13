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
