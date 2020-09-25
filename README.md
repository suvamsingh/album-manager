# album-manager
album manager to manage albums and photos


Steps to launch the whole application

       FOR ALBUM-MANAGER

1. git clone https://github.com/suvamsingh/album-manager.git
2. cd album-manager

3. docker-compose -f .\docker-compose.yml up -d

** we might need to create the topic for kafka manually here follow the below two steps

1. docker exec -it kafka /bin/sh  

check if image_notification topic is present or not 
./kafka-topics.sh --list --zookeeper zookeeper:2181 

if not present run
2. ./kafka-topics.sh --create --zookeeper zookeeper:2181  --replication-factor 1 --partitions 1 --topic image_notification




       FOR NOTIFICATION SERVICE


1. git clone https://github.com/suvamsingh/notification.git

Launch producer api

2. cd notification 
3. go run main.go

Launch consumer

1. cd notification
2. go run worker/main.go

