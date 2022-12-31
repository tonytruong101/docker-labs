## React Dockerfile
FROM node:14
WORKDIR /app
COPY ./build/server.js /app
COPY . /app
EXPOSE 3000
CMD ["npm", "start"]
