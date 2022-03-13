FROM becivells/gobase-1.7 as builder

RUN go install -v github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest



FROM alpine

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.subfinder.src="https://github.com/projectdiscovery/subfinder" \
      tools.subfinder.desc="Subfinder is a subdomain discovery tool that discovers valid subdomains for websites by using passive online sources. " \
      version=0.0.1

COPY --from=builder /root/go/bin/ /usr/local/bin/

RUN mkdir /app
WORKDIR /app/

CMD ["/usr/local/bin/subfinder"]
