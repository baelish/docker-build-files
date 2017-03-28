FROM alpine-with-testing-repo:latest
RUN apk add djbdns dnscache daemontools
RUN deluser dnscache && adduser -D dnscache && adduser -D dnslog
RUN rm -rf /etc/dnscache && dnscache-conf dnscache dnslog /etc/dnscache/ 0.0.0.0
ADD ./start-dnscache /start-dnscache
RUN chmod +x /start-dnscache
EXPOSE 53/udp
EXPOSE 53
CMD ["/start-dnscache"]
