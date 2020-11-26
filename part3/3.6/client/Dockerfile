FROM node:lts-alpine as build-stage

WORKDIR /app

COPY ./frontend-example-docker-master /app

ENV API_URL=http://localhost:8000
ENV NODE_ENV=production

RUN npm install && \
  npm run build

FROM nginx:alpine

COPY --from=build-stage /app/dist/ /usr/share/nginx/html

CMD ["nginx", "-g", "daemon off;"]