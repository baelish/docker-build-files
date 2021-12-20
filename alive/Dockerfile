FROM golang:alpine as builder
RUN apk add git
ARG CACHEBUST=
ARG VERSION=v0.2.3
RUN go install github.com/baelish/alive@"$VERSION"

FROM alpine:latest
RUN mkdir /app /data
WORKDIR /app
COPY --from=builder /go/bin/alive .
CMD ./alive -b /data/
