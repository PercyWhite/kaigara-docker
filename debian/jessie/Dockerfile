FROM dockette/jessie as kaigara-build

ARG TARGETARCH

RUN apt-get update && apt-get -y install wget ca-certificates

RUN wget -O go.tgz https://go.dev/dl/go1.17.3.linux-${TARGETARCH}.tar.gz && tar -C /usr/local -xzf go.tgz && rm go.tgz

ENV PATH="/usr/local/go/bin:${PATH}"
ENV GOPATH="/usr/local/go"

RUN go install github.com/rubykube/kaigara@v0.0.5

FROM debian:jessie-slim

COPY --from=kaigara-build /usr/local/go/bin/kaigara /usr/local/bin/kaigara