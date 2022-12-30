## Problem

You have a simple Ruby web application that you want to run in a Docker container. The web application is built using the Sinatra framework and uses a MongoDB database to store data. You have created a Dockerfile with the following contents:

```
FROM ruby:2.7
WORKDIR /app
COPY Gemfile /app
COPY Gemfile.lock /app
RUN bundle install
COPY . /app
CMD ["ruby", "app.rb"]
```
However, when you run the docker build and docker run commands, you get an error that says "Mongo::Error::NoServerAvailable: No server is available to handle this request."


