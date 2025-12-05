# Guidewire-style fraud demo (local)

Stack: Kafka, Camel, Spark, Hadoop (HDFS), Hive, Docker Compose. Optional Kubernetes.

## Quick start
1. docker compose build camel
2. docker compose up -d
3. Init Hive:
   - docker compose exec hive-server bash
   - beeline -u jdbc:hive2://hive-server:10000
   - paste contents of hive/init.sql
4. Run Spark:
   - docker compose exec spark bash
   - pip install -r /app/requirements.txt
   - spark-submit --master local /app/streaming_job.py
5. Camel auto-publishes events from ./events to Kafka.

## Query
In Beeline:
