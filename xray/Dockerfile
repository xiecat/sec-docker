FROM becivells/gobase-1.7 as builder

# https://github.com/docker/buildx#dockerfile
# https://www.waynerv.com/posts/building-multi-architecture-images-with-docker-buildx/
ARG TARGETARCH

RUN wget https://github.com/chaitin/xray/releases/download/$(curl -s https://api.github.com/repos/chaitin/xray/releases/latest|jq .name|tr -d '\"\nXRAY ')/xray_linux_${TARGETARCH}.zip \
    && unzip xray_linux_${TARGETARCH}.zip &&chmod 755 xray_linux_${TARGETARCH} &&mkdir -p /root/go/bin/&& mv xray_linux_${TARGETARCH} /root/go/bin/xray



FROM becivells/alpine-chromium

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.xray.src="https://github.com/chaitin/xray" \
      tools.xray.desc="xray 是一款功能强大的安全评估工具" \
      version=0.0.2

COPY --from=builder /root/go/bin/ /usr/local/bin/
RUN apk add  --no-cache libpcap-dev && mkdir /app
WORKDIR /app/

CMD ["/usr/local/bin/xray"]
