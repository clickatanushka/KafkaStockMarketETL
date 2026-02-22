# 🚀 Kafka Stock Market Real-Time Data Pipeline

## 📌 Project Overview

This project demonstrates a real-time data engineering pipeline using Apache Kafka and AWS services.

The system simulates live stock market data, streams it through Kafka, stores it in Amazon S3, catalogs it using AWS Glue, and enables SQL-based querying through Amazon Athena.

This project mimics a real-world financial data streaming architecture.

---

## 🏗️ Architecture Flow

1. Stock data simulated in real-time from CSV
2. Kafka Producer sends streaming data to a topic
3. Kafka Consumer processes the data
4. Processed data uploaded to Amazon S3
5. AWS Glue Crawler creates schema metadata
6. Amazon Athena runs SQL queries on the data

---

## 🛠️ Tech Stack

- Python
- Apache Kafka
- AWS EC2
- Amazon S3
- AWS Glue Crawler
- Amazon Athena
- Jupyter Notebook

---

## 📂 Project Structure

KafkaStockMarketPipeline/

├── producer/  
│   ├── produce_stock.py  
│   └── utils.py  

├── consumer/  
│   ├── consume_stock.py  
│   └── process_data.py  

├── notebooks/  
│   ├── real_time_simulation.ipynb  
│   └── data_analysis.ipynb  

├── s3_scripts/  
│   ├── upload_to_s3.py  
│   └── s3_config.py  

├── crawler/  
│   ├── crawler_main.py  
│   └── crawler_config.py  

├── athena_queries/  
│   ├── query_stock.sql  
│   └── query_summary.sql  

├── docs/  
│   └── architecture.png  

├── requirements.txt  
├── README.md  
└── .gitignore  

---

## ⚙️ How to Run the Project

### 1️⃣ Start Kafka (on EC2)

```bash
zookeeper-server-start.sh config/zookeeper.properties
kafka-server-start.sh config/server.properties
