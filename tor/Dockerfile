FROM alpine:latest
MAINTAINER SwissTengu <tengu@tengu.ch>

ADD files/repositories /etc/apk/repositories
RUN apk update
RUN apk add libevent@edge
RUN apk add tor@testing
ADD files/torrc /etc/tor/torrc

EXPOSE 9050 9040 5400
CMD ["/usr/bin/tor", "-f", "/etc/tor/torrc"]
