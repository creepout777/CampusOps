FROM eclipse-temurin:25-jdk-alpine
WORKDIR /app
COPY mvnw .
COPY .mvn .mvn
COPY pom.xml .
RUN chmod +x mvnw && ./mvnw dependency:go-offline -B
COPY src src
RUN ./mvnw clean package -DskipTests
EXPOSE 8080

# Use exact JAR filename instead of wildcard
CMD ["java", "-jar", "target/CampusOps-0.0.1-SNAPSHOT.jar"]
