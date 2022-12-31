## Problem

You have a simple React web application that you want to run in a Docker container. The web application is built using the create-react-app tool and uses a Node.js server to serve the application. You have created a Dockerfile with the following contents:

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
However, when you run the docker build and docker run commands, you get an error that says 'failed to compute cache key: "/package-lock.json" not found: not found'".

**Challenge**:

1. Resolve the docker build command 
1. Be able to visit the simple-react-app locally in your web-browser.

**Hint:**

You'll need to create a simple react app.
