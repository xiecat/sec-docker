FROM becivells/gobase-1.7 as builder

RUN go install -v github.com/projectdiscovery/proxify/cmd/proxify@latest



FROM alpine

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.proxify.src="https://github.com/projectdiscovery/proxify" \
      tools.proxify.desc="Swiss Army Knife Proxy for rapid deployments. Supports multiple operations such as request/response dump, filtering and manipulation via DSL language, upstream HTTP/Socks5 proxy. Additionally a replay utility allows to import the dumped traffic (request/responses with correct domain name) into burp or any other proxy by simply setting the upstream proxy to proxify." \
      version=0.0.2

COPY --from=builder /root/go/bin/ /usr/local/bin/
RUN mkdir /app
WORKDIR /app/

CMD ["/usr/local/bin/proxify"]