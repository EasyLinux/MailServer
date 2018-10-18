FROM alpine:3.8
LABEL Description="Serveur de messagerie" \
      author="Serge NOEL <serge.noel@net6a.com>"

RUN mkdir -p /Data/Dovecot.Imap
RUN ln -s /Data/Dovecot.Imap /etc/dovecot

RUN apk update
RUN apk add dovecot-ldap
# Attention Génération clé /etc/ssl/dovecot/server.key
RUN rm -rf /Data/Dovecot.Imap
#ADD Files/ /

VOLUME /Data
EXPOSE 143
CMD ["/usr/sbin/dovecot","-F"]
