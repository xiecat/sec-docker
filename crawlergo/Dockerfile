FROM becivells/gobase-1.7 as builder

RUN mkdir -p ${GOPATH}/src/ && mkdir -p ${GOPATH}/bin/  \
    && cd ${GOPATH}/src/ &&  git clone   https://github.com/Qianlitp/crawlergo \
    && cd crawlergo && go build -o crawlergo cmd/crawlergo/crawlergo_cmd.go \
    && mv crawlergo ${GOPATH}/bin



FROM becivells/alpine-chromium

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.crawlergo.src="https://github.com/Qianlitp/crawlergo" \
      tools.crawlergo.desc="A powerful browser crawler for web vulnerability scanners" \
      version=0.0.1

COPY --from=builder /root/go/bin/ /usr/local/bin/
RUN mkdir /app
WORKDIR /app/

CMD ["/usr/local/bin/crawlergo"]