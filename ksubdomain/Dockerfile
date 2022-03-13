FROM becivells/gobase-1.7 as builder


RUN go install -v github.com/boy-hack/ksubdomain/cmd/ksubdomain@latest



FROM alpine

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.ksubdomain.src="https://github.com/boy-hack/ksubdomain" \
      tools.ksubdomain.desc="ksubdomain是一款基于无状态的子域名爆破工具" \
      version=0.0.1

COPY --from=builder /root/go/bin/ /usr/local/bin/
RUN apk add  --no-cache libpcap-dev && mkdir /app
WORKDIR /app/

CMD ["/usr/local/bin/ksubdomain"]