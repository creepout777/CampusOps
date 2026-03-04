# ------------------------
# Build stage
# ------------------------
FROM eclipse-temurin:25-jdk-alpine AS builder
WORKDIR /app

# Copy Maven wrapper
COPY mvnw .
COPY .mvn .mvn
COPY pom.xml .

# Download dependencies offline
RUN chmod +x mvnw && ./mvnw dependency:go-offline -B

# Copy source code
COPY src src

# Build the JAR
RUN ./mvnw clean package -DskipTests

# ------------------------
# Run stage
# ------------------------
FROM eclipse-temurin:25-jdk-alpine
WORKDIR /app

# Copy the built JAR from the builder stage
COPY --from=builder /app/target/backend-0.0.1-SNAPSHOT.jar app.jar

# Expose port
EXPOSE 8080

# Run the app
CMD ["java", "-jar", "app.jar"]
