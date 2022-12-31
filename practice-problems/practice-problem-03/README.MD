## How to Start

Simply run a `docker-compose up -d` to setup your environment. Then Read the problem below. 

## Problem 

You have a simple React web application that you want to run in a Docker container. The web application is built using the create-react-app tool and uses a PostgresDB to save data to. 

You have created a Dockerfile with the following contents:

```
FROM node:14
WORKDIR /app
COPY package.json /app
COPY package-lock.json /app
RUN npm install
COPY . /app
EXPOSE 3000
CMD ["npm", "start"]
```

You also have a `docker-compose.yaml` file that has been configured like so:

```
version: '3'
services:
  postgres:
    image: postgis/postgis
    container_name: postgres-database-container
    ports:
            - 5432:5432
    restart: always
    environment:
      POSTGRES_DB: postgres
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: postgres
```

However, when you execute `docker run` to start your new React Web application, then trying to validate your application connection to the PostgresDB Docker Container with `docker exec <container_name> bash -c pg_isready -h 0.0.0.0 -U postgres -d practice_test_db` 

Returns the following error:

**0.0.0.0:5432 - rejecting connections**

## Challenge

1. Resolve any `docker build` errors
1. Resolve any `docker run` errors.
1. Resolve `rejecting connections error`

**Hint:**

1. You'll want to inspect the PostgresDB container to see what has been setup or what hasn't been setup. Never assume everything is created.
1. You'll want to inspect your react Dockerfile.


