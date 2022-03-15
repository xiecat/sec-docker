FROM becivells/alpine-gcc as builder

RUN  wget https://codeload.github.com/blechschmidt/massdns/zip/master -O /home/massdns.zip

RUN  cd /home/ && unzip massdns.zip && mv massdns-master massdns && cd massdns && make



FROM python:3.9-alpine

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.massdns.src="https://github.com/blechschmidt/massdns" \
      tools.massdns.desc="A high-performance DNS stub resolver." \
      version=0.0.2

COPY --from=builder /home/massdns/bin/ /usr/local/bin/

RUN  mkdir /app

WORKDIR /app/