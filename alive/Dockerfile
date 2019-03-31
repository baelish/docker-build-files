FROM golang:alpine as builder
RUN apk add git
ARG CACHEBUST=
RUN go get github.com/baelish/alive

FROM alpine:latest
RUN mkdir /app /data
WORKDIR /app
COPY --from=builder /go/bin/alive .
CMD ./alive -b /data/
