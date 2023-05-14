# ##########################################################################################
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

# FROM node:lts-alpine
# WORKDIR /app
# COPY ./dist/apps/expressapp .
# COPY ./package.json ./yarn.lock ./
# ENV PORT=3333
# EXPOSE ${PORT}
# RUN yarn install --production
# # dependencies that express needs
# RUN yarn install reflect-metadata tslib rxjs express
# CMD node ./main.js

# docker build -f ./apps/expressapp/Dockerfile . -t expressapp
# docker run -d -p 3333:3333 expressapp
# docker images --format "table {{.ID}}\t{{.Tag}}\t{{.Repository}}"
# kubectl apply -f apps/expressapp/deployment.json 
# docker stop