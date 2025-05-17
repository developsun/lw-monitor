# 🦉 Apache Kafka with KRaft Mode (ZooKeeper-less) using Docker

This setup runs **Apache Kafka 3.6+** in **KRaft mode** (Kafka Raft metadata mode) using Docker Compose. It is ideal for local development and lightweight testing environments.

## 📦 Features

- Kafka running in **KRaft mode** (no ZooKeeper)
- Lightweight single-node setup
- Full Kafka CLI access
- Optional Kafka UI (Kafdrop)

## ✅ Prerequisites

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

## ⚙️ Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/developsun/lw-monitor.git
cd kafka-service
```

### 2. Replace the UUID 

You can generate a UUID for **KAFKA_KRAFT_CLUSTER_ID** via:

```bash
uuidgen
```

### 3. Start Kafka in KRaft mode:

```bash
docker-compose up -d
```
Access UI at: **http://localhost:9000**

### 4. Check kafka container logs

```bash
docker logs -f kafka
```

### 4. Stop Kafka Service

```bash
docker-compose down -v
```

## 🧪 Setup Instructions

### ✅ Enter the Kafka container

```bash
docker exec -it kafka bash
```

### ✅ Enter the Kafka container

```bash
docker exec -it kafka bash
```

### 📌 Create a Topic

```bash
kafka-topics.sh \
  --create \
  --topic test-topic \
  --bootstrap-server localhost:9092 \
  --partitions 3 \
  --replication-factor 1
```

### 📃 List Topics

```bash
kafka-topics.sh \
  --list \
  --bootstrap-server localhost:9092
```

### 📨 Produce Messages

```bash
kafka-console-producer.sh \
  --broker-list localhost:9092 \
  --topic test-topic
```
Then start typing messages. Press **Enter** after each.

Exit with **Ctrl+C.**

### 📬 Consume Messages

```bash
kafka-console-consumer.sh \
  --bootstrap-server localhost:9092 \
  --topic test-topic \
  --from-beginning
```
Exit with **Ctrl+C**.

