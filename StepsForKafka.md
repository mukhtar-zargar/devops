# Kafka Steps

- Download kafka binary.tgz
- Extract kafka .tgz file
- Copy the path of the Kafka folder. Now go to config inside kafka folder and open zookeeper.properties file. Copy the path against the field 'dataDir' and add /zookeeper-data to the path.
- Now in the same folder config open server.properties and scroll down to log.dirs and paste the path. To the path add /kafka-logs
- Change dir to kafka in powershell/terminal
- Run in one shell session:

  ```powershell
  .\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties

  ```

- Open another shell session and run:

  ```powershell
  .\bin\windows\kafka-server-start.bat .\config\server.properties

  ```

- To create a topic in shell:

  ```powershell
  .\bin\windows\kafka-topics.bat --create --topic {{topic-name}} --bootstrap-server localhost:9092
  ```

  _--describe: to describe the topic created_

- To run producer in shell:

  ```powershell
  .\bin\windows\kafka-console-producer.bat --topic {{topic-name}} --bootstrap-server localhost:9092

  ```

- To run consumer in shell:

  ```powershell
  .\bin\windows\kafka-console-consumer.bat --topic {{topic-name}} --from-beginning --bootstrap-server localhost:9092 --partition 0
  ```

  _--partition 0: (trick) only if consumer doesn't consume data properly_

- Produce AVRO messages to kafka by passing an avro schema id

  ```bash
  kafka-avro-console-producer --broker-list host.docker.internal:9092 --topic integration-yara-digitalsolution-polaris --property schema.registry.url=host.docker.internal:8081 --property value.schema.id=13
  ```
