FROM alpine:3.7

ARG TARGETARCH

RUN apk add --no-cache libc6-compat
RUN wget -O go.tgz https://go.dev/dl/go1.17.3.linux-${TARGETARCH}.tar.gz && tar -C /usr/local -xzf go.tgz && rm go.tgz

ENV PATH="/usr/local/go/bin:${PATH}"
ENV GOPATH="/usr/local/go"

RUN go install github.com/rubykube/kaigara@v0.0.5

RUN cp ${GOPATH}/bin/kaigara /usr/local/bin/kaigara