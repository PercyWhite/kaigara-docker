FROM golang:alpine3.16 as kaigara-build

RUN go install github.com/rubykube/kaigara@v0.0.5

FROM alpine:3.16

COPY --from=kaigara-build /go/bin/kaigara /usr/local/bin/kaigara