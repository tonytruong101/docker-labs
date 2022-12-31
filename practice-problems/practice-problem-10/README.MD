
## Problem 
Create a simple Node.js web application that displays "Hello, World!" on a web page.

Here is the start of what a simple NodeJs Dockerfile would look like:

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
```

## Challenge

1. Successfully bring up your application with `docker-compose up -d`
1. Be able to visit your application with `localhost:port`
1. Application displays `hello-world` .

**Hint:**

1. You'll need to look into setting up a basic hello world application.
