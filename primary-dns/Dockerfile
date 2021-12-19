FROM alpine:latest

RUN echo "http://dl-4.alpinelinux.org/alpine/edge/testing" >> /etc/apk/repositories && \
  apk --no-cache update && \
  apk --no-cache upgrade && \
  apk --no-cache add daemontools djbdns make tinydns

RUN deluser tinydns && \
  adduser -D tinydns && \
  adduser -D dnslog

RUN rm -rf /etc/tinydns && \
  tinydns-conf tinydns dnslog /etc/tinydns/ 0.0.0.0

ADD ./start-tinydns /start-tinydns
RUN chmod +x /start-tinydns

EXPOSE 53/udp
EXPOSE 53
CMD ["/start-tinydns"]
