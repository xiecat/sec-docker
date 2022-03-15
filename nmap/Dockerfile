FROM alpine:latest

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.nmap.src="https://pkgs.alpinelinux.org/package/edge/main/x86/nmap" \
      tools.massdns.desc="network exploration tool and security/port scanner." \
      version=0.0.2

RUN apk add --no-cache nmap nmap-scripts nmap-ncat

RUN  mkdir /app

WORKDIR /app/