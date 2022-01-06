FROM osixia/openldap

LABEL maintainer="cameron.shiell@mirada-medical.com"

ENV LDAP_ORGANISATION="Mirada Test" \
    LDAP_DOMAIN="mirada-medical.test" \
    LDAP_ADMIN_PASSWORD="nocturnalWorm30"

COPY bootstrap.ldif /container/service/slapd/assets/config/bootstrap/ldif/50-bootstrap.ldif
