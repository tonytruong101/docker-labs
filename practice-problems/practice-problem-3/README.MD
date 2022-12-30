## Problem

You have a simple Python web application that you want to run in a Docker container. The web application is built using the Flask framework and uses a MySQL database to store data. You have created a Dockerfile with the following contents:

```
FROM python:3
WORKDIR /app
COPY requirements.txt /app
RUN pip install -r requirements.txt
COPY . /app
CMD ["python", "app.py"]
```
However, when you run the docker build and docker run commands, you get an error that says "OperationalError: (2003, "Can't connect to MySQL server on 'db' (111)")".

How do your resolve this error?

