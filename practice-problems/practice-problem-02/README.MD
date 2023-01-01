## Problem Set

You have a simple React and Node.js web application that you want to run in a Docker container. The web application is built using the create-react-app tool and uses a Node.js server to serve the application. You have created a React Dockerfile with the following contents:

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

You have a `docker-compose.yaml` that has been configured like this:

```
version: '3'
services:
  backend:
    image: node
    privileged: true
    user: root
    container_name: node-backend-service
    tty: true
    stdin_open: true
    ports:
      - 3000:3000
```

However, after you run `docker-compose up -d` then you run the docker build and docker run commands, you get an error that says 

**"Error: listen EADDRINUSE: address already in use :::3000"**.

## Challenge

1. Resolve any `docker build` errors
1. Resolve the `docker run` error
