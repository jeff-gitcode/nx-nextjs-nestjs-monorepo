##########################################################################################
FROM node:lts-alpine

WORKDIR /app

COPY dist/apps/expressapp .

ENV PORT=3333

EXPOSE ${PORT}

RUN yarn install

# dependencies that nestjs needs
# RUN yarn add reflect-metadata tslib rxjs helmet cache-manager @nestjs/platform-express @nestjs/common @nestjs/core @nestjs/swagger @nestjs/terminus @nestjs/throttler @nestjs/config @nestjs/axios @nestjs/cqrs
RUN yarn add tslib express

CMD node ./main.js

# docker build -f ./apps/expressapp/Dockerfile . -t expressapp
# docker run -d -p 3333:3333 expressapp
# docker stop