# Configurazione di vaultwarden

Storage personale di password e note

### Parametri di configurazione
- configurazione traefik
    - "traefik.enable=true" (attiviamo traefik)
    - "traefik.http.routers.vaultwarden.rule=Host(`vaultwarden.local`)" (impostiamo il dominio)
    - "traefik.http.routers.vaultwarden.entrypoints=web, websecure" (impostiamo le porte di entrata 80 e 443)
    - "traefik.http.routers.vaultwarden.tls=true" (attiviamo il certificato SSL)
- environment:
      - SIGNUPS_ALLOWED=false (Blocca la registrazione di altri utenti)
