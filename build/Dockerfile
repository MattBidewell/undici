FROM node:21-alpine@sha256:40e95eba13b7b06b14210abbf9d9d3e26f46303808510ea33afc970e845ef1e4

ARG UID=1000
ARG GID=1000

RUN apk add -U clang lld wasi-sdk
RUN mkdir /home/node/undici

WORKDIR /home/node/undici

COPY package.json .
COPY build build
COPY deps deps
COPY lib lib

RUN npm i

USER node
