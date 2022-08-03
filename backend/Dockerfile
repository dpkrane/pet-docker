FROM openjdk:20-slim
WORKDIR /app
COPY . .
RUN chmod +x mvnw && ./mvnw clean package -DskipTests
EXPOSE 8080
CMD ["java","-jar","target/studentsystem-0.0.1-SNAPSHOT.jar"]