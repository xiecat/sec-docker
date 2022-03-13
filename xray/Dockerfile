FROM becivells/gobase-1.7 as builder

RUN wget https://github.com/chaitin/xray/releases/download/$(curl -s https://api.github.com/repos/chaitin/xray/releases/latest|jq .name|tr -d '\"\nXRAY ')/xray_linux_amd64.zip \
    && unzip xray_linux_amd64.zip &&chmod 755 xray_linux_amd64 &&mkdir -p /root/go/bin/&& mv xray_linux_amd64 /root/go/bin/xray



FROM becivells/alpine-chromium

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.xray.src="https://github.com/chaitin/xray" \
      tools.xray.desc="xray 是一款功能强大的安全评估工具" \
      version=0.0.1

COPY --from=builder /root/go/bin/ /usr/local/bin/
RUN apk add  --no-cache libpcap-dev && mkdir /app
WORKDIR /app/

CMD ["/usr/local/bin/xray"]