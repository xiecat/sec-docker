FROM becivells/gobase-1.7 as builder

RUN go install -v github.com/tomnomnom/anew@latest

FROM alpine

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.anew.src="https://github.com/tomnomnom/anew" \
      tools.anew.desc="Append lines from stdin to a file, but only if they don't already appear in the file. Outputs new lines to stdout too, making it a bit like a tee -a that removes duplicates." \
      version=0.0.2

COPY --from=builder /root/go/bin/ /usr/local/bin/

RUN mkdir /app/
WORKDIR /app/

CMD ["/usr/local/bin/anew"]
