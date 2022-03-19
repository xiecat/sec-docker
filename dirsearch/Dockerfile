FROM python:3.9-alpine

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.dirsearch.src="https://github.com/maurosoria/dirsearch" \
      tools.dirsearch.desc="An advanced command-line tool designed to brute force directories and files in webservers, AKA web path scanner" \
      version=0.0.1

RUN  apk add --no-cache --virtual .build-deps \
        gcc \
        musl-dev \
        libffi-dev \
        openssl-dev \
        libffi-dev \
        && wget https://codeload.github.com/maurosoria/dirsearch/zip/master -O /home/dirsearch.zip \
        &&  cd /home/ && unzip dirsearch.zip && mv dirsearch-master dirsearch && cd dirsearch \
        && pip install -r requirements.txt \
        && apk del .build-deps \
        &&  rm -rf /home/dirsearch.zip && rm -rf /tmp/*

RUN mkdir /app
WORKDIR  /app

CMD ["python","/home/dirsearch/dirsearch.py"]