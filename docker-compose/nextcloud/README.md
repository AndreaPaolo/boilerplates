# Configurazione di nextcloud

Self hosted google drive

### Parametri di configurazione
- configurazione permessi
    - PGID=1000 (si trovano scrivendo `id` nel terminale della macchina)
    - PUID=1000
- configurazione del timezone
    - TZ=Europe/Rome
- configurazione traefik
    - "traefik.enable=true" (attiviamo traefik)
    - "traefik.http.routers.nextcloud.rule=Host(`nextcloud.local`)" (impostiamo il dominio)
    - "traefik.http.routers.nextcloud.entrypoints=web, websecure" (impostiamo le porte di entrata 80 e 443)
    - "traefik.http.routers.nextcloud.tls=true" (attiviamo il certificato SSL) 