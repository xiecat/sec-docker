FROM becivells/gobase-1.7 as builder

RUN go install -v github.com/projectdiscovery/httpx/cmd/httpx@latest



FROM alpine

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.httpx.src="https://github.com/projectdiscovery/httpx" \
      tools.httpx.desc="httpx is a fast and multi-purpose HTTP toolkit allow to run multiple probers using retryablehttp library, it is designed to maintain the result reliability with increased threads." \
      version=0.0.2

COPY --from=builder /root/go/bin/ /usr/local/bin/
RUN mkdir /app
WORKDIR /app/

CMD ["/usr/local/bin/httpx"]