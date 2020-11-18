FROM node:12-alpine AS stage-one

WORKDIR /service

# Install DEB dependencies and others.
RUN apk add --no-cache alpine-sdk python py-pip linux-headers

COPY package.json .
COPY yarn.lock .
RUN yarn install --frozen-lockfile


COPY server.js .
COPY config.js .
COPY lib lib

CMD ["node", "/service/server.js"]
