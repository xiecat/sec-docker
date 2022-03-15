FROM alpine:latest

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      version=0.0.1

RUN  echo "http://dl-cdn.alpinelinux.org/alpine/edge/main" > /etc/apk/repositories \
    && echo "http://dl-cdn.alpinelinux.org/alpine/edge/community" >> /etc/apk/repositories \
    && echo "http://dl-cdn.alpinelinux.org/alpine/edge/testing" >> /etc/apk/repositories \
    && apk upgrade -U -a \
    && apk add --no-cache \
     gcc \
     musl-dev \
    libstdc++ \
    make \
    && rm -rf /var/cache/* \
    && mkdir /var/cache/apk
