FROM becivells/gobase-1.7 as builder

#ENV GOPROXY=https://goproxy.cn

RUN go install -v github.com/projectdiscovery/naabu/v2/cmd/naabu@latest



FROM alpine

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.naabu.src="https://github.com/projectdiscovery/naabu" \
      tools.naabu.desc="Naabu is a port scanning tool written in Go that allows you to enumerate valid ports for hosts in a fast and reliable manner. It is a really simple tool that does fast SYN/CONNECT scans on the host/list of hosts and lists all ports that return a reply." \
      version=0.0.1

COPY --from=builder /root/go/bin/ /usr/local/bin/
RUN apk add  --no-cache libpcap-dev && mkdir /app
WORKDIR /app/

CMD ["/usr/local/bin/naabu"]
