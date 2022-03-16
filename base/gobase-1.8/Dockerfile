FROM golang:1.18-alpine as builder

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      version=0.0.3

ENV GOROOT="/usr/local/go"
ENV GOPATH="/root/go"
ENV PATH="${PATH}:${GOROOT}/bin:${GOPATH}/bin"
ENV CGO_ENABLED=1

RUN apk  add curl git gcc  libc-dev  libpcap-dev jq
