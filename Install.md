# Installing Kirkland
## Java
Need Java 1.8 or better
https://www.azul.com/downloads/?package=jdk#download-openjdk

## Kafaka
Download and verify

    curl -O https://dlcdn.apache.org/kafka/KEYS
    curl -O https://dlcdn.apache.org/kafka/3.1.0/kafka_2.12-3.1.0.tgz.asc
    curl -O https://dlcdn.apache.org/kafka/3.1.0/kafka_2.12-3.1.0.tgz
    gpg --import KEYS
    gpg --verify kafka_2.12-3.1.0.tgz.asc kafka_2.12-3.1.0.tgz
    cd kafka_2.12-3.1.0
    bin/zookeeper-server-start.sh config/zookeeper.properties
  
Open up a new terminal

    cd kafka_2.12-3.1.0
    bin/kafka-server-start.sh config/server.properties
  
Open a new terminal and test

    bin/kafka-topics.sh --create --topic quickstart-events --bootstrap-server localhost:9092
    # enter some stuff, newline is a new item, ctrl-c to exit
    bin/kafka-console-producer.sh --topic quickstart-events --bootstrap-server localhost:9092 
    # see what you entered, ctrl-c to exit
    bin/kafka-console-consumer.sh --topic quickstart-events --from-beginning --bootstrap-server localhost:9092
 
 
## Rust
The programing language 

        curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
