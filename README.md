# documents

## Open Source Kafka Startup in local ##

1.Create Storage in Kafka
``` bin\windows\kafka-storage.bat format -t 769f88f8-d3bb-4a75-83ef-55f7a9349f0e -c config\kraft\server.properties```


2. Start Kafka Server / Broker
``` bin\windows\kafka-server-start.bat config\kraft\server.properties ```

3. Create topic
  ``` .\bin\windows\kafka-topics.bat --bootstrap-server localhost:9092 --create --topic test-topic --partitions 1 --replication-factor 1 ```
4. list out all topic names

    ``` .\bin\windows\kafka-topics.bat --bootstrap-server localhost:9092 --list ```

5. Describe topics
  
    ``` bin\windows\kafka-topics.bat --bootstrap-server localhost:9092 --describe --topic my-topic ```

6. Produce message

    ```  bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic test-topic  ```


7. consume message

    ``` .\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic test-topic --from-beginning ```


## Confluent Kafka Community Edition in local ##

1. Start Zookeeper Server

    ```bin/zookeeper-server-start etc/kafka/zookeeper.properties```

2. Start Kafka Server / Broker

    ```bin/kafka-server-start etc/kafka/server.properties```

3. Create topic

    ```bin/kafka-topics --bootstrap-server localhost:9092 --create --topic NewTopic1 --partitions 3 --replication-factor 1```

4. list out all topic names

    ``` bin/kafka-topics --bootstrap-server localhost:9092 --list ```

5. Describe topics
  
    ``` bin/kafka-topics --bootstrap-server localhost:9092 --describe --topic NewTopic1 ```

6. Produce message

    ```bin/kafka-console-producer --broker-list localhost:9092 --topic NewTopic1```


7. consume message

    ```bin/kafka-console-consumer --bootstrap-server localhost:9092 --topic NewTopic1 --from-beginning ```
    
8. Send CSV File data to kafka    

   ```bin/kafka-console-producer --broker-list localhost:9092 --topic NewTopic1 <bin/customers.csv```
   
   
