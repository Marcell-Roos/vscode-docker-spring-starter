# Use a base image with Java 21
FROM openjdk:21-jdk-slim

# Set up the environment for Java
ENV JAVA_HOME=/docker-java-home
RUN ln -s "$(dirname "$(readlink -f "$(which java)")")" /docker-java-home

RUN apt-get update -qq && apt-get install -yq --no-install-recommends \
    git

# Set the working directory in the container
WORKDIR /app

# Copy the Spring Boot project files into the container
COPY . .

# Expose the default Spring Boot port
EXPOSE 8081

# Default command
CMD ["./mvnw", "spring-boot:run"]