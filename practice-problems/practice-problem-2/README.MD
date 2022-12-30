You have a simple Node.js web server that you want to run in a Docker container. The web server listens on port 3000 and serves a message that says "Hello, World!". You have created a Dockerfile with the following contents:

```
FROM node:10
WORKDIR /app
COPY package.json /app
RUN npm install
COPY . /app
CMD ["node", "index.js"]
```

However, when you run the docker build and docker run commands, you get an error that says "Error: listen EADDRINUSE: address already in use :::3000".

How should you resolve this issue?


