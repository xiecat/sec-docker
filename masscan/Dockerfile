FROM becivells/alpine-gcc as builder

RUN apk add --update linux-headers
RUN  cd /home/ && unzip masscan.zip && mv masscan-master masscan && cd masscan && make



FROM python:3.9-alpine

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.massdns.src="https://github.com/robertdavidgraham/masscan" \
      tools.massdns.desc="This is an Internet-scale port scanner. It can scan the entire Internet in under 5 minutes, transmitting 10 million packets per second, from a single machine" \
      version=0.0.1

COPY --from=builder /home/masscan/bin/ /usr/local/bin/
RUN apk add  --no-cache libpcap-dev && mkdir /app

WORKDIR /app/