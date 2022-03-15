FROM becivells/gobase-1.7 as builder

RUN go install -v github.com/OWASP/Amass/v3/...@master

FROM alpine

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.amass.src="https://github.com/OWASP/Amass" \
      tools.amass.desc="The OWASP Amass Project performs network mapping of attack surfaces and external asset discovery using open source information gathering and active reconnaissance techniques." \
      version=0.0.2

COPY --from=builder /root/go/bin/ /usr/local/bin/

RUN mkdir /app/
WORKDIR /app/

CMD ["/usr/local/bin/amass"]