FROM python:3.9-alpine

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.pocsuite3.src="https://github.com/knownsec/pocsuite3" \
      tools.pocsuite3.desc="Usage of pocsuite3 for attacking targets without prior mutual consent is illegal. pocsuite3 is for security testing purposes only" \
      version=0.0.1

RUN  apk add --no-cache --virtual .build-deps \
        gcc \
        musl-dev \
        && pip3 install pocsuite3 \
        && apk del .build-deps

RUN mkdir /app
WORKDIR  /app

CMD ["/usr/local/bin/pocsuite"]