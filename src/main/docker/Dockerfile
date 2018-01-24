FROM java:openjdk-8-jre-alpine

RUN apk update && apk upgrade && apk add bash

ENV KAFKA_ADDRESS=master.mesos:9092 \
    CONSUMER_GROUP="" \
    KAFKA_TOPIC="" \
    PARTITION="" \
    OFFSET=""
#WAIT_ARGS=8.8.8.8:80;ontimeuaaserver:9999

# add directly the war
ADD *spring-boot.jar /app.jar

RUN sh -c 'touch /app.jar'
WORKDIR /
CMD java -Djava.security.egd=file:/dev/./urandom -jar /app.jar