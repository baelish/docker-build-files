FROM baelish/alpine-with-testing-repo:latest
RUN apk add daemontools djbdns make tinydns
RUN deluser tinydns && adduser -D tinydns && adduser -D dnslog
RUN rm -rf /etc/tinydns && tinydns-conf tinydns dnslog /etc/tinydns/ 0.0.0.0
ADD ./start-tinydns /start-tinydns
RUN chmod +x /start-tinydns
EXPOSE 53/udp
EXPOSE 53
CMD ["/start-tinydns"]
