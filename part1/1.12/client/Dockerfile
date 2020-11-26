FROM ubuntu:16.04

WORKDIR /myapp
COPY ./frontend-example-docker-master /myapp
RUN apt-get update && apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_lts.x | bash
RUN apt-get update && apt-get install -y nodejs
RUN npm install
EXPOSE 5000
ENV API_URL=http://localhost:8000
CMD npm start
