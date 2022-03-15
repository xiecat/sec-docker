FROM alpine:latest

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      version=0.0.2

#fork https://github.com/Zenika/alpine-chrome
# Installs latest Chromium package.
RUN  echo "http://dl-cdn.alpinelinux.org/alpine/edge/main" > /etc/apk/repositories \
    && echo "http://dl-cdn.alpinelinux.org/alpine/edge/community" >> /etc/apk/repositories \
    && echo "http://dl-cdn.alpinelinux.org/alpine/edge/testing" >> /etc/apk/repositories \
    && apk upgrade -U -a \
    && apk add \
    libstdc++ \
    chromium \
    harfbuzz \
    nss \
    freetype \
    ttf-freefont \
    font-noto-emoji \
    wqy-zenhei \
    py3-pip \
    && rm -rf /var/cache/* \
    && mkdir /var/cache/apk

COPY local.conf /etc/fonts/local.conf

ENV CHROME_BIN=/usr/bin/chromium-browser \
    CHROME_PATH=/usr/lib/chromium/ \
    CRAWLERGO_CHROMIUM_PATH=/usr/bin/chromium-browser
