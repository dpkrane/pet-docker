FROM openjdk:16-alpine3.13 as build
WORKDIR /project
COPY .mvn/ .mvn
COPY mvnw pom.xml ./
RUN chmod +x mvnw && ./mvnw dependency:go-offline
COPY src ./src
RUN ./mvnw package

FROM openjdk:16-alpine3.13
WORKDIR /app
COPY --from=build /project/target/*.jar /app/app.jar
EXPOSE 8080
CMD ["java", "-jar", "app.jar"]
