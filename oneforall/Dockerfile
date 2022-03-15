FROM becivells/massdns  as builder

FROM python:3.9-alpine

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.oneforall.src="https://github.com/shmilylty/OneForAll" \
      tools.oneforall.desc="one for all subdomain" \
      version=0.0.1

RUN  apk add --no-cache --virtual .build-deps \
        gcc \
        musl-dev \
        && wget https://codeload.github.com/shmilylty/OneForAll/zip/master -O /home/oneforall.zip \
        &&  cd /home/ && unzip oneforall.zip&&mv OneForAll-master oneforall && cd oneforall \
        && pip install -r requirements.txt  \
        && apk del .build-deps \
        &&  rm -rf /home/oneforall.zip && rm -rf /tmp/*

RUN rm -rf /home/oneforall/thirdparty/massdns/*

COPY --from=builder /usr/local/bin/massdns /home/oneforall/thirdparty/massdns/massdns_linux_x86_64

RUN mkdir /app
WORKDIR  /app

CMD ["python","/home/oneforall/oneforall.py"]