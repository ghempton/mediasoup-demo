FROM node:10 AS stage-one

WORKDIR /service

# Install DEB dependencies and others.
RUN \
	set -x \
	&& apt-get update \
	&& apt-get install -y net-tools build-essential valgrind

COPY package.json .
COPY yarn.lock .
RUN yarn install --frozen-lockfile


COPY server.js .
COPY config.js .
COPY lib lib

CMD ["node", "/service/server.js"]
