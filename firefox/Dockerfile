FROM alpine:latest
MAINTAINER SwissTengu <tengu@tengu.ch>

ADD files/repositories /etc/apk/repositories
RUN apk update
RUN apk add firefox
RUN apk add openssh 
RUN apk add xauth
RUN apk add perl
RUN apk add shadow@testing
RUN apk add dbus
RUN apk add expect
RUN apk add ttf-dejavu ttf-liberation ttf-freefont ttf-opensans@testing ttf-droid

RUN mkdir -p /var/run/sshd

RUN adduser -s /bin/sh -h /home/docker -D -g 'ssh user' docker
RUN mkdir -p /home/docker/.ssh
RUN chmod 0700 /home/docker/.ssh
RUN chown -R docker: /home/docker/.ssh
RUN mkpasswd -l 20 docker
RUN usermod -U docker

ADD files/startup /usr/local/bin/startup
RUN chmod 0750 /usr/local/bin/startup

RUN mkdir -p /home/docker/.cache/mozilla/firefox
RUN chown -R docker: /home/docker/.cache
ADD files/sshd_config /etc/ssh/sshd_config

ENV NOTVISIBLE "in users profile"
RUN echo "export VISIBLE=now" >> /etc/profile

EXPOSE 22
CMD ["/usr/local/bin/startup"]
