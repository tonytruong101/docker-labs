## Problem
You have a simple Java web application that you want to run in a Docker container. The web application is built using the Spring framework and uses a PostgreSQL database to store data. You have created a Dockerfile with the following contents:

```
FROM openjdk:8-jdk-alpine
WORKDIR /app
COPY build/libs/my-web-app.jar /app
CMD ["java", "-jar", "my-web-app.jar"]
```

