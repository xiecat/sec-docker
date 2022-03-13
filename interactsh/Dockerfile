FROM becivells/gobase-1.7 as builder

RUN go install -v github.com/projectdiscovery/interactsh/cmd/interactsh-client@latest



FROM alpine

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.interactsh.src="https://github.com/projectdiscovery/interactsh" \
      tools.interactsh.desc="Interactsh is an open-source tool for detecting out-of-band interactions. It is a tool designed to detect vulnerabilities that cause external interactions." \
      version=0.0.2

COPY --from=builder /root/go/bin/ /usr/local/bin/
RUN mkdir /app
WORKDIR /app/

CMD ["/usr/local/bin/interactsh-client"]