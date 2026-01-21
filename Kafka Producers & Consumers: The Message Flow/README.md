# Kafka Producers and Consumers –

This README explains **Kafka Producers and Consumers** in a **clear and beginner-friendly way**, focused on **basic understanding**, not deep internals.

---

## 1. Kafka Producer

A **Kafka Producer** is an application that **sends (publishes) messages to Kafka**.

### Simple definition

> A producer is a program that **writes data to Kafka topics**.

### What a producer does

* Creates messages (events)
* Sends messages to a Kafka topic
* Does NOT care who consumes the data

### Example events sent by producers

* Order placed
* Payment completed
* Log generated
* User login event

### Simple flow

```
Producer → Topic → Kafka
```

### Key points about producers

* Producers send data to **topics**, not directly to consumers
* Kafka decides which **partition** the message goes to
* Producers are usually applications or services

### Real-world example

* A web application sending order events to Kafka
* A server sending logs to Kafka

---

## 2. Kafka Consumer

A **Kafka Consumer** is an application that **reads (subscribes to) messages from Kafka**.

### Simple definition

> A consumer is a program that **reads data from Kafka topics**.

### What a consumer does

* Subscribes to one or more topics
* Reads messages from partitions
* Processes the data (store, analyze, forward, etc.)

### Simple flow

```
Kafka → Topic → Consumer
```

### Key points about consumers

* Consumers pull data from Kafka (Kafka does not push)
* Consumers read messages using **offsets**
* Consumers can read at their own speed

### Real-world example

* Analytics service reading events
* Monitoring system reading logs
* Notification service reading order events

---

## 3. Producer and Consumer Together

### End-to-end flow

```
Producer → Topic → Partitions → Broker → Consumer
```

### Step-by-step explanation

1. Producer sends a message
2. Message goes to a topic
3. Topic stores message in a partition
4. Partition is stored on a broker
5. Consumer reads message from broker

---

## 4. Consumer Groups (Basic Idea)

A **consumer group** is a group of consumers that **share the work of reading data**.

### Why consumer groups are needed

* To scale message processing
* To avoid duplicate processing

### Important rule

* One partition is read by **only one consumer** in a consumer group

### Example

* Topic has 3 partitions
* Consumer group has 3 consumers
* Each consumer reads one partition

---

## 5. Differences Between Producer and Consumer

| Producer               | Consumer          |
| ---------------------- | ----------------- |
| Sends data             | Reads data        |
| Writes to topics       | Reads from topics |
| Pushes messages        | Pulls messages    |
| Does not track offsets | Tracks offsets    |

---

## 6. One-Line Interview Answers

* **Producer**: An application that sends messages to Kafka topics
* **Consumer**: An application that reads messages from Kafka topics
* **Consumer Group**: A group of consumers that share message processing

---

## 7. Scope Clarification

This README covers **Kafka basics only**:

* Producer
* Consumer
* Consumer group (basic idea)

Not included:

* Producer acknowledgements
* Exactly-once semantics
* Kafka Streams
* Advanced offset management

---

