## Project

You have a simple Rust web server that you want to run in a Docker container. The web server listens on port 80 and serves a message that says "Hello, World!". You have created a Dockerfile with the following contents:

```
FROM rust:1.53
WORKDIR /app
COPY . /app
RUN cargo build --release
CMD ["./target/release/my-web-server"]
```

However, when you run the docker build and docker run commands, you get an error that says "standard_init_linux.go:211: exec user process caused "permission denied"".


