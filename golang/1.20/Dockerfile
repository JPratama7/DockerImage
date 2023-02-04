FROM golang:1.20-alpine3.17 as build

RUN rm -rf .git LICENSE README.md \
    && apk add --no-cache g++ musl-dev