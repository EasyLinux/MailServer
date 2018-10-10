FROM alpine:3.8
LABEL Description="Serveur de messagerie" \
      author="Serge NOEL <serge.noel@net6a.com>"

RUN apk update
RUN apk add dovecot-ldap
# Attention Génération clé /etc/ssl/dovecot/server.key
ADD Files/ /




CMD ["/usr/sbin/dovecot","-F"]
