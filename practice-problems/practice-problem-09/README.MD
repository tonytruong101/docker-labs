
## Problem 
Create a simple Flask web application that displays the current time on a web page.

Here is the start of what a simple Flask Dockerfile would look like:

```
FROM python:3.9
WORKDIR /app
COPY requirements.txt /app
RUN pip install -r requirements.txt
COPY . /app
EXPOSE 5000
CMD ["flask", "run", "--host=0.0.0.0"]
```
Here is the start of a what a `docker-compose.yaml` configuration would look like:

```
version: '3'
services:
  web:
    build:
      context: .
      dockerfile: ./Dockerfile
    ports:
      - "5000:5000"
```

## Challenge

1. Successfully bring up your application with `docker-compose up -d`
1. Be able to visit your application with `localhost:port`
1. Application displays the current time.

**Hint:**

1. You'll need to look into setting up a basic flask application.
