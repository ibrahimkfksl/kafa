#Docker üzerinden zookeper kurulumu:

docker run --name zookeeper -p 2181:2181 zookeeper

#Docker üzerinden kafka kurulumu

docker run --name kafka -p 9092:9092 -e KAFKA_ZOOKEEPER_CONNECT=[your-local-ip-address]:2181 -e KAFKA_ADVERTISED_LISTENERS=PLAINTEXT://[your-local-ip-address]:9092 -e KAFKA_OFFSETS_TOPIC_REPLICATION_FACTOR=1 confluentinc/cp-kafka

#Proje çalıştırma:

- npm install
- node topic.js [kod içerisindeki ip adresleri local ip adres ile güncellenmeli]
- node producer.js [Topic Name] [Partition Index]
- node consumer.js [Topic Name]