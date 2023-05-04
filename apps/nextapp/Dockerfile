FROM node:lts-alpine as deps

RUN apk add --no-cache libc6-compat

WORKDIR /app

COPY dist/apps/nextapp/package.json ./

RUN npm install --omit=dev && npm install sharp@^0.31.2

FROM node:lts-alpine as runner

RUN apk add --no-cache dumb-init

ENV NODE_ENV production

ENV PORT 3000

WORKDIR /app

COPY --from=deps /app/node_modules ./node_modules

COPY --from=deps /app/package.json ./package.json

COPY dist/apps/nextapp ./

EXPOSE 3000

ENV NEXT_TELEMETRY_DISABLED 1

CMD ["dumb-init", "node_modules/.bin/next", "start"]

# docker build -f ./apps/nextapp/Dockerfile . -t nextapp
# docker run -d -p 3000:3000 nextapp