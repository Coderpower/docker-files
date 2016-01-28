FROM coderpower/node:4.2.4

MAINTAINER Lancelot Prigent <lancelot.prigent@gmail.com>

RUN npm install -g mocha@2.3.4
RUN rm -rf npm_cache /tmp/*

ENV NODE_PATH /usr/local/lib/node_modules/

ENV ENGINE mocha
ENV ENGINE_VERSION 2.3.4

WORKDIR /src

# CMD mocha test --recursive -R json-stream
