## Problem

You have a simple PHP web application that you want to run in a Docker container. The web application is built using the Laravel framework and uses a Redis cache to store data. You have created a Dockerfile with the following contents:

```
FROM php:7.4-apache
WORKDIR /app
COPY . /app
RUN chown -R www-data:www-data /app
CMD ["apache2-foreground"]
```
However, when you run the docker build and docker run commands, you get an error that says "ErrorException: Connection refused [tcp://redis:6379]".

