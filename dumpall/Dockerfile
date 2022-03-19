FROM python:3.9-alpine

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.dumpall.src="https://github.com/0xHJK/dumpall" \
      tools.dumpall.desc="支持多种泄漏情况利用" \
      version=0.0.1

RUN  apk add --no-cache --virtual .build-deps \
        gcc \
        musl-dev \
        && wget https://codeload.github.com/0xHJK/dumpall/zip/master -O /home/dumpall.zip \
        &&  cd /home/ && unzip dumpall.zip&&mv dumpall-master dumpall && cd dumpall \
        && pip install -r requirements.txt  \
        && apk del .build-deps \
        &&  rm -rf /home/dumpall.zip && rm -rf /tmp/*

RUN mkdir /app
WORKDIR  /app

CMD ["python","/home/dumpall/dumpall.py"]