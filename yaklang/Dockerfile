FROM alpine

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.yaklang.src="https://www.yaklang.io/" \
      tools.yaklang.desc="北半球最强的 web 安全研发脚本语言" \
      version=0.0.1

RUN cd /usr/local/bin/ && wget https://yaklang.oss-accelerate.aliyuncs.com/yak/latest/yak_linux_amd64 \
    && chmod 755 yak_linux_amd64 && mv yak_linux_amd64 yak

RUN mkdir /app/
WORKDIR /app/

CMD ["/usr/local/bin/yak"]
