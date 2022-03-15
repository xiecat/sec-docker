FROM becivells/gobase-1.7 as builder

RUN mkdir -p ${GOPATH}/src/ && mkdir -p ${GOPATH}/bin/  \
    && cd ${GOPATH}/src/ &&  git clone   https://github.com/zhzyker/dismap \
    && cd dismap && go build -o dismap cmd/dismap/dismap.go \
    && mv dismap ${GOPATH}/bin



FROM alpine

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.dismap.src="https://github.com/zhzyker/dismap" \
      tools.dismap.desc="Dismap positioning is an asset discovery and identification tool." \
      version=0.0.3

COPY --from=builder /root/go/bin/ /usr/local/bin/
RUN mkdir /app
WORKDIR /app/

CMD ["/usr/local/bin/dismap"]