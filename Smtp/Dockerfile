FROM alpine:3.8
LABEL author="Serge NOEL <serge.noel@net6a.com>"

RUN mkdir -p /Data/Postfix
RUN ln -s /Data/Postfix /etc/postfix
RUN ls -l /etc
RUN apk update \
    && apk add postfix postfix-ldap

ADD Files/ /

RUN mkdir -p /Data/Maildir

RUN addgroup -g 5000 mailservice
RUN adduser -h /Data/Maildir -g "Mail Service" -u 5000 -G mailservice -D mailservice
RUN chown mailservice: /Data/Maildir

VOLUME /Data
EXPOSE 25

# DEBUG
RUN apk add busybox-extras nano mc

CMD ["/usr/sbin/postfix","start-fg"]
#CMD sleep 7200
