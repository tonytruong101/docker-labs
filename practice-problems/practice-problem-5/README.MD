## Problem

You have a simple Go web server that you want to run in a Docker container. The web server listens on port 8080 and serves a message that says "Hello, World!". You have created a Dockerfile with the following contents:

```
FROM golang:1.15
WORKDIR /app
COPY . /app
RUN go build -o main .
CMD ["./main"]
```
However, when you run the docker build and docker run commands, you get an error that says "standard_init_linux.go:211: exec user process caused "no such file or directory"".


