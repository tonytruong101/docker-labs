
## Problem 
Create a simple React web application that allows users to add, edit, and delete notes. The notes should be stored in a PostgreSQL database.

Here is the start of what a simple react Dockerfile would look like:

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
Here is the start of a what a `docker-compose.yaml` configuration would look like:

```
version: '3'
services:
  web:
    build:
      context: .
      dockerfile: ./Dockerfile
    ports:
      - "3000:3000"
    depends_on:
      - db
  db:
    image: postgres
    environment:
      POSTGRES_DB: postgres
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: postgres
```

## Challenge

1. Successfully bring up your application with `docker-compose up -d`
1. Be able to visit your application with `localhost:port`
1. Be able to perform basic CRUDs with your application. 

**Hint:**

1. You'll need to look into setting up a function to fetch records.
