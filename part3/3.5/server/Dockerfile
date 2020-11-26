FROM node:lts-alpine

WORKDIR /app

COPY ./backend-example-docker-master /app

ENV NODE_ENV=production
ENV FRONT_URL=http://localhost:5000

RUN npm install 

USER node 

EXPOSE 8000

CMD ["npm", "start"]
