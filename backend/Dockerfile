FROM maven:amazoncorretto AS build
WORKDIR /app
COPY . .
RUN mvn clean package

FROM openjdk:10-jre-slim
WORKDIR /opt/to-do-app/ 
COPY --from=build /app/target/to-do-listEntity-app-0.0.1-SNAPSHOT.jar /opt/to-do-app/
EXPOSE 8080
CMD ["java", "-jar", "to-do-listEntity-app-0.0.1-SNAPSHOT.jar"]
