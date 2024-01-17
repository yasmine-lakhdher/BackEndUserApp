#FROM openjdk:19
#WORKDIR /app
#COPY ./target/Project-0.0.1-SNAPSHOT.jar /app
#RUN chmod 755 /app/Project-0.0.1-SNAPSHOT.jar
#EXPOSE 9091
#CMD ["java", "-jar", "Projet-0.0.1-SNAPSHOT.jar"]
#ENTRYPOINT ["java", "-jar", "Projet-0.0.1-SNAPSHOT.jar"]

FROM eclipse-temurin:17-jdk-focal
 
WORKDIR /app
 
COPY .mvn/ .mvn
COPY mvnw pom.xml ./
RUN ./mvnw dependency:go-offline
 
COPY src ./src
EXPOSE 9091

CMD ["./mvnw", "spring-boot:run"]
