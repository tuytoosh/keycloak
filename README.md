# Keycloak Docker compose setup, TSL enabled

Keycloak is an open source identity and access management solution. In this repo you can see pre-configured setup for Keycloak + Postgres and instructions to enable TSL for it.

## To issue TSL with OpenSSL 

In order to make SSL self-signed keys run the following commands:

```
openssl genpkey -algorithm RSA -out keycloak.key -aes256
openssl req -new -key keycloak.key -out keycloak.csr
openssl x509 -req -days 365 -in keycloak.csr -signkey keycloak.key -out keycloak.crt
```

Then you can access keycloak on `https://<YOUR_IP>:8443`