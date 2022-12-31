## How to Start

Simply run a `docker-compose up -d` to setup your environment. Then Read the problem below. 

## Problem 
You have a simple Node.js web application that you want to run in a Docker container and serve using nginx. You have created a Dockerfile for the web application with the following contents:

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
You also have a Dockerfile for nginx with the following contents:

```
FROM nginx:1.19
COPY nginx.conf /etc/nginx/nginx.conf
```
However, when you run the docker-compose build and docker-compose up commands, you get an error.

## Challenge

1. Resolve any `docker build` errors
1. Resolve any `docker-compose up -d` errors
1. Successfully bring up your application with `docker-compose up -d`
1. Be able to visit your application with `localhost:port`

## Bonus Challenge

1. Be able to visit your website in your browse using only `localhost` without specifying the port.

**Hint:**

1. You'll want to inspect your react Dockerfile.
1. You'll want to look into Nginx Rules to complete the Bonus Challenge
