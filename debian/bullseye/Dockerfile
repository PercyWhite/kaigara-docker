FROM golang:bullseye as kaigara-build

RUN go install github.com/rubykube/kaigara@v0.0.5

FROM debian:bullseye-slim

COPY --from=kaigara-build /go/bin/kaigara /usr/local/bin/kaigara