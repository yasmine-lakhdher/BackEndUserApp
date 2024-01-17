FROM openjdk:19
WORKDIR /app
COPY ./target/Project-0.0.1-SNAPSHOT.jar /app
RUN chmod 755 /app/Project-0.0.1-SNAPSHOT.jar
EXPOSE 9091
#CMD ["java", "-jar", "Projet-0.0.1-SNAPSHOT.jar"]
ENTRYPOINT ["java", "-jar", "Projet-0.0.1-SNAPSHOT.jar"]
