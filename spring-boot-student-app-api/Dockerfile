FROM maven:3.9-eclipse-temurin-21 as buildstep
WORKDIR /app
COPY . .
RUN mvn clean install

FROM eclipse-temurin:21-jre
COPY --from=buildstep /app/target/student-app-api-0.0.1-SNAPSHOT.jar /usr/share/myservice/
ENTRYPOINT ["java", "-jar", "/usr/share/myservice/student-app-api-0.0.1-SNAPSHOT.jar"]
EXPOSE 8080
