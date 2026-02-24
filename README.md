# Real-Time Data Pipeline using Apache Kafka on AWS


This project implements an end-to-end real-time data streaming pipeline using Apache Kafka deployed on AWS EC2. 
Streaming data is ingested via Kafka producers, stored in Amazon S3, cataloged using AWS Glue, 
and queried using Amazon Athena for analytics.


## Features

- Real-time event ingestion
- Fault-tolerant streaming
- Scalable cloud storage
- Serverless querying

---
## Architecture
EC2 (Kafka + Zookeeper)
→ Kafka Topic
→ Producer / Consumer
→ Amazon S3
→ AWS Glue Crawler
→ AWS Athena

##  How to Run the Project

Step 1: Start Zookeeper
bin/zookeeper-server-start.sh config/zookeeper.properties

Step 2: Start Kafka
bin/kafka-server-start.sh config/server.properties

Step 3: Create Topic
bin/kafka-topics.sh --create \
--topic realtime-topic \
--bootstrap-server localhost:9092 \
--partitions 1 \
--replication-factor 1

Step 4: Run Producer
python producer.py

Step 5: Run Consumer
python consumer.py

Terminal output
<img width="1920" height="1080" alt="Screenshot From 2026-02-19 15-12-48" src="https://github.com/user-attachments/assets/e29093ab-0e64-4ad2-a95d-35f268398a71" />

## Real-Time Streaming Demonstration

### Kafka Producer & Consumer
<img width="1219" height="688" alt="Screenshot From 2026-02-25 01-25-29" src="https://github.com/user-attachments/assets/c0fe8826-d9fd-4061-860d-17817d372aeb" />

<img width="1219" height="687" alt="Screenshot From 2026-02-25 01-26-43" src="https://github.com/user-attachments/assets/45fdc6ea-44e7-4654-aee6-aae097c3e6d6" />


### Data Stored in S3
Objects right now observed 39
<img width="1218" height="709" alt="Screenshot From 2026-02-25 01-28-28" src="https://github.com/user-attachments/assets/076390ee-2df8-4e66-9096-0ba205dc0026" />

Objects right now observed 157
<img width="1230" height="727" alt="Screenshot From 2026-02-25 01-29-15" src="https://github.com/user-attachments/assets/9e3039b3-8288-43d3-b2df-5ad504d05547" />


### Glue Catalog
Glue Crawler
<img width="1216" height="672" alt="Screenshot From 2026-02-25 01-31-13" src="https://github.com/user-attachments/assets/81bf9252-e522-41e3-b492-d09fd4539316" />


### Athena Query Results
Athena Output – 91 rows

<img width="1216" height="672" alt="Screenshot From 2026-02-25 01-31-13" src="https://github.com/user-attachments/assets/51d835dc-6fe5-4e0b-acee-3f2ad86e1f72" />

Athena Output now you can observe the rows executed right now is 144 <img width="1221" height="675" alt="Screenshot From 2026-02-25 01-33-45" src="https://github.com/user-attachments/assets/9df840cd-20b3-4097-aec4-3e99bb16ab75" />

## Tech Stack

- Apache Kafka
- AWS EC2
- Amazon S3
- AWS Glue
- AWS Athena
- Python
- JupyterLab
- Linux (Unix Shell)

- ## Key Learnings

- Implemented real-time event streaming architecture
- Managed distributed message brokers on cloud infrastructure
- Integrated Kafka with AWS storage services
- Performed serverless SQL analytics using Athena
