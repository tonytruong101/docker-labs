## Problem

You have a simple Elixir web application that you want to run in a Docker container. The web application is built using the Phoenix framework and uses a PostgreSQL database to store data. You have created a Dockerfile with the following contents:

```
FROM elixir:1.10
WORKDIR /app
COPY mix.exs /app
COPY mix.lock /app
RUN mix deps.get
COPY . /app
RUN mix compile
CMD ["mix", "phx.server"]
```
However, when you run the docker build and docker run commands, you get an error that says "** (DBConnection.ConnectionError) owner #PID<0.8.0> timed out because it was waiting for the database to be ready. The database might still be starting up."**

