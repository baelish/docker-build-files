FROM alpine:latest

RUN apk --no-cache update && \
  apk --no-cache upgrade && \
  apk --no-cache add dhcp

RUN adduser -D dhcpd
ADD ./start-dhcpd /start-dhcpd

EXPOSE 67-68/udp
CMD ["/start-dhcpd"]
