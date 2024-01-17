#FROM openjdk:19
#WORKDIR /app
#COPY ./target/Project-0.0.1-SNAPSHOT.jar /app
#RUN chmod 755 /app/Project-0.0.1-SNAPSHOT.jar
#EXPOSE 9091
#CMD ["java", "-jar", "Projet-0.0.1-SNAPSHOT.jar"]
#ENTRYPOINT ["java", "-jar", "Projet-0.0.1-SNAPSHOT.jar"]

FROM maven:3.8.4-openjdk-11-slim AS build
# Set the working directory in the container
WORKDIR /app
# Copy the pom.xml and the project files to the container
COPY pom.xml .
COPY src ./src
# Build the application using Maven
RUN mvn clean package -DskipTests
# Use an official OpenJDK image as the base image
FROM openjdk:11-jre-slim
# Set the working directory in the container
WORKDIR /app
# Copy the built JAR file from the previous stage to the container
COPY - from=build /app/target/Projet-0.0.1-SNAPSHOT.jar .
# Set the command to run the application
CMD ["java", "-jar", "Projet-0.0.1-SNAPSHOT.jar"]
