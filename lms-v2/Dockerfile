#FROM openjdk:19
#WORKDIR /app
#COPY ./target/Project-0.0.1-SNAPSHOT.jar /app
#RUN chmod 755 /app/Project-0.0.1-SNAPSHOT.jar
#EXPOSE 9091
#CMD ["java", "-jar", "Projet-0.0.1-SNAPSHOT.jar"]
#ENTRYPOINT ["java", "-jar", "Projet-0.0.1-SNAPSHOT.jar"]

FROM maven:3.9.6 AS maven
#LABEL MAINTAINER="sgwebfreelancer@gmail.com"

WORKDIR /usr/src/app
COPY . /usr/src/app
# Compile and package the application to an executable JAR
RUN mvn package 

# For Java 11, 
FROM openjdk:19

ARG JAR_FILE=Projet-0.0.1-SNAPSHOT.jar

WORKDIR /opt/app

# Copy the spring-boot-api-tutorial.jar from the maven stage to the /opt/app directory of the current stage.
COPY --from=maven /usr/src/app/target/${JAR_FILE} /opt/app/

ENTRYPOINT ["java","-jar","Projet-0.0.1-SNAPSHOT.jar"]
