FROM becivells/gobase-1.7 as builder

RUN go install -v github.com/projectdiscovery/chaos-client/cmd/chaos@latest



FROM alpine

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.chaos.src="https://github.com/projectdiscovery/chaos-client" \
      tools.chaos.desc="Go client to communicate with Chaos dataset API." \
      version=0.0.1

COPY --from=builder /root/go/bin/ /usr/local/bin/
RUN mkdir /app
WORKDIR /app/

CMD ["/usr/local/bin/chaos"]