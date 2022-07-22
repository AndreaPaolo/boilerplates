# Configurazione di heidmall

Homepage per la gestione dei servizi di una homelab

### Parametri di configurazione
- configurazione permessi
    - PGID=1000 (si trovano scrivendo `id` nel terminale della macchina)
    - PUID=1000
- configurazione del timezone
    - TZ=Europe/Rome
- configurazione traefik
    - "traefik.enable=true" (attiviamo traefik)
    - "traefik.http.routers.heimdall.rule=Host(`heimdall.local`)" (impostiamo il dominio)
    - "traefik.http.routers.heimdall.entrypoints=web, websecure" (impostiamo le porte di entrata 80 e 443)
    - "traefik.http.routers.heimdall.tls=true" (attiviamo il certificato SSL)