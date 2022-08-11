FROM openjdk:16-alpine3.13 as build
WORKDIR /project
COPY . /project
RUN chmod +x mvnw && ./mvnw clean package -DskipTests

FROM openjdk:16-alpine3.13
WORKDIR /app
COPY --from=build /project/target/*.jar /app/app.jar
EXPOSE 8080
CMD ["java", "-jar", "app.jar"]
