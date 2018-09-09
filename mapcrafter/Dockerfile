FROM alpine-with-repo:latest
RUN apk update
RUN apk add curl python
ADD ./start-mapcrafter /start-mapcrafter
RUN chmod +x /start-mapcrafter
CMD ["/start-mapcrafter"]

