FROM becivells/gobase-1.7 as builder

RUN go install -v github.com/xiecat/fofax/cmd/fofax@latest



FROM alpine

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.fofax.src="https://github.com/xiecat/fofax" \
      tools.fofax.desc="fofax is a fofa query tool written in go, positioned as a command-line tool and characterized by simplicity and speed." \
      version=0.0.1

COPY --from=builder /root/go/bin/ /usr/local/bin/

RUN mkdir /app/
WORKDIR /app/

CMD ["/usr/local/bin/fofax"]