# Image based on debian named 'build'
FROM openjdk:8 as build

WORKDIR /app
# Copy the sources into the container
COPY ./spring-example-project-master /app
# Run the build on the jdk container
RUN ./mvnw package 

# Image based on Debian slim without the build tools
FROM openjdk:8-jre-slim
# Copy just the build artifacts
COPY --from=build /app/target/docker-example-1.1.3.jar /app/
# Create an unpriviliged user 
RUN useradd -m app
# Run the app as the unpriviliged user
USER app
WORKDIR /app

EXPOSE 8080

CMD ["java", "-jar", "./docker-example-1.1.3.jar"]
