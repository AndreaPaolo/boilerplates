# Configurazione di Uptime kuma
Monitor per servizi

### Parametri di configurazione
- configurazione traefik
    - "traefik.enable=true" (attiviamo traefik)
    - "traefik.http.routers.kuma.rule=Host(`kuma.local`)" (impostiamo il dominio)
    - "traefik.http.services.kuma.loadbalancer.server.port=3001" (impostiamo la porta)
    - "traefik.http.routers.kuma.entrypoints=web, websecure" (impostiamo le porte di entrata 80 e 443)
    - "traefik.http.routers.kuma.tls=true" (attiviamo il certificato SSL)