# FROM tomcat:9-jre8-alpine

# RUN apk --update add curl ca-certificates tar 
# RUN set -x \
#     && mkdir /home/mysql \
#     && curl -fSL https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.40.tar.gz -o /home/mysql/mysql-connector.jar \
#     && cd /home/mysql \
#     && tar -xzvf mysql-connector.jar \
#     && pwd \
#     && mkdir -p /usr/share/java \
#     && mv /home/mysql/mysql-connector-java-5.1.40/mysql-connector-java-5.1.40-bin.jar /usr/share/java/mysql-connector-java.jar \
#     && cd /home \
#     && rm -R *

# RUN export CLASSPATH=$CLASSPATH:/usr/share/java/mysql-connector-java.jar
# #ADD target/*.jar app.jar
# ADD ./target/myshuttledev-tests.jar /usr/local/tomcat/webapps/myshuttledev.war

FROM openjdk:8-jdk-alpine
VOLUME /tmp
EXPOSE 8080
ADD target/*.jar app.jar
ENV JAVA_OPTS=""
ENTRYPOINT [ "sh", "-c", "java $JAVA_OPTS -Djava.security.egd=file:/dev/./urandom -jar /app.jar" ]

