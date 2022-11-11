FROM osixia/openldap

LABEL maintainer="cameron@shiell.co.uk"

ENV LDAP_ORGANISATION="Amanshu" \
    LDAP_DOMAIN="amanshu.test" \
    LDAP_ADMIN_PASSWORD="nocturnalWorm30"

COPY bootstrap.ldif /container/service/slapd/assets/config/bootstrap/ldif/50-bootstrap.ldif
