# Use a lightweight OpenJDK 17 image
FROM openjdk:17-jdk-slim

# Set the working directory to /app
WORKDIR /app

# Copy the JAR file into the container at /app
COPY target/crud-application-0.0.1-SNAPSHOT.jar /app/app.jar

# Expose the port your application will run on
EXPOSE 8091

# Specify the command to run on container start
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
