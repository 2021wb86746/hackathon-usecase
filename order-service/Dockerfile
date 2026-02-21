# Use a Java base image
FROM openjdk:17-jdk-slim

# Set the working directory
WORKDIR /app

# Copy the Maven build files and download dependencies
# This helps in caching dependencies
COPY pom.xml .
RUN mvn dependency:go-offline

# Copy the rest of the application source code
COPY src ./src

# Package the application
RUN mvn package -DskipTests

# Define the command to run your app
# IMPORTANT: Replace 'order-service-0.0.1-SNAPSHOT.jar' with your actual JAR file name
# You'll find the exact name in your 'target' directory after a local build.
ENTRYPOINT ["java","-jar","/app/target/order-service-0.0.1-SNAPSHOT.jar"]

# Expose the port your Java app runs on (e.g., 8080 is common for Spring Boot)
EXPOSE 8080
