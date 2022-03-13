FROM becivells/gobase-1.7 as builder

RUN go install -v github.com/projectdiscovery/dnsx/cmd/dnsx@latest



FROM alpine

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.dnsx.src="https://github.com/projectdiscovery/dnsx" \
      tools.dnsx.desc="dnsx is a fast and multi-purpose DNS toolkit allow to run multiple probes using retryabledns library, that allows you to perform multiple DNS queries of your choice with a list of user supplied resolvers, additionally supports DNS wildcard filtering like shuffledns." \
      version=0.0.2

COPY --from=builder /root/go/bin/ /usr/local/bin/

RUN apk add  --no-cache libpcap-dev && mkdir /app
WORKDIR /app/

CMD ["/usr/local/bin/dnsx"]
