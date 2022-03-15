FROM python:3.9-alpine

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.massdns.src="https://github.com/zmap/zmap" \
      tools.massdns.desc="This is an Internet-scale port scanner. It can scan the entire Internet in under 5 minutes, transmitting 10 million packets per second, from a single machine" \
      version=0.0.2


RUN apk add  --no-cache zmap && mkdir /app/

WORKDIR /app/