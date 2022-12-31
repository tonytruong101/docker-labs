
## Problem 
Create a simple Node.js web application that displays a list of books on a web page. The books should be stored in a MongoDB database.

Here is the start of what a simple nodeJs Dockerfile would look like:

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
    image: mongo
    environment:
      MONGO_INITDB_ROOT_USERNAME: root
      MONGO_INITDB_ROOT_PASSWORD: password

```

## Challenge

1. Create a simple MongoDB with records for the booklist
1. Resolve any `docker-compose up -d` errors
1. Successfully bring up your application with `docker-compose up -d`
1. Be able to visit your application with `localhost:port`

**Hint:**

1. You'll need to look into fetching records
