FROM ubuntu:16.04

WORKDIR /app

COPY ./frontend-example-docker-master /app
RUN apt-get update && apt-get install -y curl && \
  curl -sL https://deb.nodesource.com/setup_lts.x | bash && \
  apt-get update && apt-get install -y nodejs && \
  npm install && \
  apt-get purge -y --auto-remove curl && \ 
  rm -rf /var/lib/apt/lists/* && \ 
  useradd -m app && \
  chown -R app:app /app


USER app 

EXPOSE 5000

ENV API_URL=http://localhost:8000

CMD ["npm", "start"]
