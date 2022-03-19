FROM python:3.9-alpine

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.vulmap.src="https://github.com/zhzyker/vulmap" \
      tools.vulmap.desc="Vulmap is a web vulnerability scanning and verification tool that can scan webapps for vulnerabilities and has vulnerability exploitation functions" \
      version=0.0.1


RUN  apk add --no-cache --virtual .build-deps \
        gcc \
        musl-dev \
        && wget https://codeload.github.com/zhzyker/vulmap/zip/main -O /home/vulmap.zip \
        &&  cd /home/ && unzip vulmap.zip && mv vulmap-main vulmap && cd vulmap \
        && pip install -r requirements.txt \
        && apk del .build-deps \
        &&  rm -rf /home/vulmap.zip && rm -rf /tmp/*



RUN mkdir /app
WORKDIR  /app

CMD ["python","/home/vulmap/vulmap.py"]