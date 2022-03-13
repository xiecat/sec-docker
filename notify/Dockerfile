FROM becivells/gobase-1.7 as builder

RUN go install -v github.com/projectdiscovery/notify/cmd/notify@latest



FROM alpine

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.notify.src="https://github.com/projectdiscovery/notify" \
      tools.notify.desc="Notify is a Go-based assistance package that enables you to stream the output of several tools (or read from a file) and publish it to a variety of supported platforms." \
      version=0.0.1

COPY --from=builder /root/go/bin/ /usr/local/bin/

RUN mkdir /app/
WORKDIR /app/

CMD ["/usr/local/bin/notify"]
