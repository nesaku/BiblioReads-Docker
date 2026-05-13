FROM alpine AS clone
WORKDIR /app

RUN apk update \
    && apk add git \
    && git clone --depth=1 https://github.com/nesaku/BiblioReads.git .

FROM node:alpine AS build
WORKDIR /app
COPY --from=clone /app/ /app/

RUN npm install \
    && npm run build

FROM node:alpine AS deploy
WORKDIR /app

ENV NEXT_TELEMETRY_DISABLED 1

COPY --from=build /app/package.json /app/package.json
COPY --from=build /app/next.config.js /app/next.config.js
COPY --from=build /app/public/ /app/public/
COPY --from=build /app/.next/ /app/.next/
COPY --from=build /app/node_modules/ /app/node_modules/

RUN mkdir -p /app/public \
    && chmod 755 /app/public \
    && touch /app/public/__ENV.js \
    && chmod 666 /app/public/__ENV.js

USER node
CMD [ "npm", "start" ]
EXPOSE 3000
