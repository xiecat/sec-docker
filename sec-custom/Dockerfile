FROM becivells/gobase-1.7 as builder

RUN go install -v github.com/projectdiscovery/httpx/cmd/httpx@latest
RUN go install -v github.com/projectdiscovery/nuclei/v2/cmd/nuclei@latest
RUN go install -v github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest
RUN go install -v github.com/projectdiscovery/naabu/v2/cmd/naabu@latest
RUN go install -v github.com/projectdiscovery/dnsx/cmd/dnsx@latest
RUN go install -v github.com/projectdiscovery/notify/cmd/notify@latest

RUN go install -v github.com/xiecat/fofax/cmd/fofax@latest
RUN go install -v github.com/boy-hack/ksubdomain/cmd/ksubdomain@latest
RUN go install -v github.com/tomnomnom/anew@latest

RUN mkdir -p ${GOPATH}/src/&& cd ${GOPATH}/src/ && git clone   https://github.com/Qianlitp/crawlergo \
    && cd crawlergo && go build -o crawlergo cmd/crawlergo/crawlergo_cmd.go \
    && mv crawlergo ${GOPATH}/bin

RUN wget https://github.com/chaitin/xray/releases/download/$(curl -s https://api.github.com/repos/chaitin/xray/releases/latest|jq .name|tr -d '\"\nXRAY ')/xray_linux_amd64.zip \
    && unzip xray_linux_amd64.zip &&chmod 755 xray_linux_amd64 && mv xray_linux_amd64 /root/go/bin/xray


RUN wget https://gosspublic.alicdn.com/ossutil/1.7.9/ossutil64 -o /root/go/bin/ossutil64 && chmod 755 /root/go/bin/ossutil64


FROM becivells/alpine-chromium

LABEL dockerfile.maintainer="becivells" \
      dockerfile.reference="https://github.com/xiecat/sec-docker" \
      tools.httpx.src="https://github.com/projectdiscovery/httpx" \
      tools.httpx.desc="httpx is a fast and multi-purpose HTTP toolkit allow to run multiple probers using retryablehttp library, it is designed to maintain the result reliability with increased threads." \
      tools.nuclei.src="https://github.com/projectdiscovery/nuclei" \
      tools.nuclei.desc="Nuclei is used to send requests across targets based on a template, leading to zero false positives and providing fast scanning on a large number of hosts. Nuclei offers scanning for a variety of protocols, including TCP, DNS, HTTP, SSL, File, Whois, Websocket, Headless etc. With powerful and flexible templating, Nuclei can be used to model all kinds of security checks." \
      tools.subfinder.src="https://github.com/projectdiscovery/subfinder" \
      tools.subfinder.desc="Subfinder is a subdomain discovery tool that discovers valid subdomains for websites by using passive online sources. " \
      tools.naabu.src="https://github.com/projectdiscovery/naabu" \
      tools.naabu.desc="Naabu is a port scanning tool written in Go that allows you to enumerate valid ports for hosts in a fast and reliable manner. It is a really simple tool that does fast SYN/CONNECT scans on the host/list of hosts and lists all ports that return a reply." \
      tools.dnsx.src="https://github.com/projectdiscovery/dnsx" \
      tools.dnsx.desc="dnsx is a fast and multi-purpose DNS toolkit allow to run multiple probes using retryabledns library, that allows you to perform multiple DNS queries of your choice with a list of user supplied resolvers, additionally supports DNS wildcard filtering like shuffledns." \
      tools.notify.src="https://github.com/projectdiscovery/notify" \
      tools.notify.desc="Notify is a Go-based assistance package that enables you to stream the output of several tools (or read from a file) and publish it to a variety of supported platforms." \
      tools.fofax.src="https://github.com/xiecat/fofax" \
      tools.fofax.desc="fofax is a fofa query tool written in go, positioned as a command-line tool and characterized by simplicity and speed." \
      tools.ksubdomain.src="https://github.com/boy-hack/ksubdomain" \
      tools.ksubdomain.desc="ksubdomain是一款基于无状态的子域名爆破工具" \
      tools.anew.src="https://github.com/tomnomnom/anew" \
      tools.anew.desc="Append lines from stdin to a file, but only if they don't already appear in the file. Outputs new lines to stdout too, making it a bit like a tee -a that removes duplicates." \
      tools.crawlergo.src="https://github.com/Qianlitp/crawlergo" \
      tools.crawlergo.desc="A powerful browser crawler for web vulnerability scanners" \
      tools.xray.src="https://github.com/chaitin/xray" \
      tools.xray.desc="xray 是一款功能强大的安全评估工具" \
      tools.ossutil.src="https://github.com/aliyun/ossutil" \
      tools.xray.desc="This tool is developed with Go and built on the official GO SDK v2.2.0 of OSS Alibaba Cloud Object Storage Service." \
      version=0.0.3

COPY --from=builder /root/go/bin/ /usr/local/bin/

RUN apk add  --no-cache libpcap-dev && nuclei -ut && mkdir /app
WORKDIR /app/