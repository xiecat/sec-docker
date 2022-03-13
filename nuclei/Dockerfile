FROM becivells/gobase-1.7 as builder

RUN go install -v github.com/projectdiscovery/nuclei/v2/cmd/nuclei@latest



FROM becivells/alpine-chromium

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.nuclei.src="https://github.com/projectdiscovery/nuclei" \
      tools.nuclei.desc="Nuclei is used to send requests across targets based on a template, leading to zero false positives and providing fast scanning on a large number of hosts. Nuclei offers scanning for a variety of protocols, including TCP, DNS, HTTP, SSL, File, Whois, Websocket, Headless etc. With powerful and flexible templating, Nuclei can be used to model all kinds of security checks." \
      version=0.0.2

COPY --from=builder /root/go/bin/ /usr/local/bin/
RUN nuclei -ut && mkdir /app
WORKDIR /app/

CMD ["/usr/local/bin/nuclei"]