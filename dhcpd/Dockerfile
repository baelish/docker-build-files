FROM baelish/alpine-with-repo:latest
RUN apk add dhcp
RUN adduser -D dhcpd
ADD ./start-dhcpd /start-dhcpd
EXPOSE 67-68/udp
CMD ["/start-dhcpd"]
