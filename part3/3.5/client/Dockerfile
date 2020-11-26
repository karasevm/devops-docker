FROM node:lts-alpine

WORKDIR /app

COPY ./frontend-example-docker-master /app

ENV API_URL=http://localhost:8000
ENV NODE_ENV=production

RUN npm install && \
  chown -R node:node /app

USER node 

EXPOSE 5000

CMD ["npm", "start"]
