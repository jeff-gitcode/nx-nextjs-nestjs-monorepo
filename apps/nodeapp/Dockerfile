##########################################################################################
FROM node:lts-alpine

WORKDIR /app

COPY dist/apps/nodeapp .

# ENV HOST=0.0.0.0
ENV PORT=3334

EXPOSE ${PORT}

RUN yarn install

# dependencies that nestjs needs
# RUN yarn add reflect-metadata tslib rxjs helmet cache-manager @nestjs/platform-express @nestjs/common @nestjs/core @nestjs/swagger @nestjs/terminus @nestjs/throttler @nestjs/config @nestjs/axios @nestjs/cqrs
RUN yarn add express

CMD node ./main.js

# docker build -f ./apps/nodeapp/Dockerfile . -t nodeapp
# docker run -d -p 3334:3334 nodeapp
# docker ps -ls
# docker stop