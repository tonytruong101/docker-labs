## How to Start

Simply run a `docker-compose up -d` to setup your environment. Then Read the problem below. 

## Problem 
You have a simple React web application that you want to run in a Docker container. The web application is built using the create-react-app tool and uses a Node.js server to serve the application. You have created a Dockerfile with the following contents:

```
FROM node:14
WORKDIR /app
COPY ./build/server.js /app
COPY . /app
EXPOSE 3000
CMD ["npm", "start"]
```
However, when you run the `docker-compose up -d` command to build your react web application, you get an error that says **failed to compute cache key: "/build/server.js" not found: not found**

## Challenge

1. Resolve any `docker build` errors
1. Successfully bring up your application with `docker-compose up -d`

**Hint:**

1. You'll want to inspect your react Dockerfile.

