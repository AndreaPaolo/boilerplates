# Configurazione di hedgedoc

Hedgedoc è la migliore piattaforma per scrivere e  condividere markdown. [Link documentazione ufficiale](https://docs.hedgedoc.org)

### Parametri di configurazione

- configurazione database
    - DB_HOST= nome del container
    - DB_USER= utente database
    - DB_PASS= password database
    - DB_NAME= nome del database
    - DB_PORT= porta (default 3306)
- configurazione permessi
    - PGID=1000 (si trovano scrivendo `id` nel terminale della macchina)
    - PUID=1000
- configurazione del timezone
    - TZ=Europe/Rome
- configurazione hedgedoc
    - CMD_DOMAIN=hedgedoc.local (url del dominio)
    - CMD_URL_ADDPORT=false (aggiunta di una porta alla fine del dominio, `false` porta non esistente)
    - CMD_PROTOCOL_USESSL=true (utilizzo del certificato SSL)
    - CMD_EMAIL=true (Login con email)
    - CMD_ALLOW_EMAIL_REGISTER=true (Registrazione tramite email)
- configurazione traefik
    - "traefik.enable=true" (attiviamo traefik)
    - "traefik.http.routers.hedgedoc.rule=Host(`hedgedoc.local`)" (impostiamo il dominio)
    - "traefik.http.routers.hedgedoc.entrypoints=web, websecure" (impostiamo le porte di entrata 80 e 443)
    - "traefik.http.routers.hedgedoc.tls=true" (attiviamo il certificato SSL)    