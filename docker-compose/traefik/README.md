# Configurazione di traefik

## Configurazione standard
Creazione di un container docker con traefik come reverse proxy, accessibile all'indirizzo ip della macchina alla porta 8080

## Volumi
- "/path/traefik:/etc/traefik" => configurazione traefik
- "/var/run/docker.sock:/var/run/docker.sock:ro" => gestione dei container 

## Certificato autocertificato
Lista dei comandi per creare un certificato

> mkdir openssl && cd openssl

> openssl req -x509 \
            -sha256 -days 356 \
            -nodes \
            -newkey rsa:2048 \
            -keyout rootCA.key -out rootCA.crt 

* Possibile errore: "Can't load /home/vagrant/.rnd into RNG"

* * RANDFILE = $ENV::HOME/.rnd in /etc/ssl/openssl.cnf

> openssl genrsa -out server.key 2048

> nano csr.conf

* [ req ]
default_bits = 2048
prompt = no
default_md = sha256
req_extensions = req_ext
distinguished_name = dn

* [ dn ]
C = IT
ST = Italia
L = 
O = AP 
OU = AP Dev
CN = dominio.com

* [ req_ext ]
subjectAltName = @alt_names

* [ alt_names ]
DNS.1 = dominio.com
DNS.2 = www.dominio.com
IP.1 = 1.1.1.1
IP.2 = 1.1.1.1

> openssl req -new -key server.key -out server.csr -config csr.conf

> nano cert.conf

* authorityKeyIdentifier=keyid,issuer
basicConstraints=CA:FALSE
keyUsage = digitalSignature, nonRepudiation, keyEncipherment, dataEncipherment
subjectAltName = @alt_names

* [alt_names]
DNS.1 = dominio.com
DNS.2 = www.dominio.com

> openssl x509 -req \
    -in server.csr \
    -CA rootCA.crt -CAkey rootCA.key \
    -CAcreateserial -out server.crt \
    -days 365 \
    -sha256 -extfile cert.conf

### Installazione certificato

- certFile: server.crt => configurazione server
- keyFile: server.key => configurazione server
- rootCA.crt => installato sul dispositivo