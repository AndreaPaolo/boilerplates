# Configurazione di portainer

Portainer come manager dei contenitori di docker

### Parametri di configurazione
- configurazione traefik
    - "traefik.enable=true" (attiviamo traefik)
    - "traefik.http.routers.portainer.rule=Host(`portainer.local`)" (impostiamo il dominio)
      - "traefik.http.services.portainer.loadbalancer.server.port=9000" (impostiamo la porta)
    - "traefik.http.routers.portainer.entrypoints=web, websecure" (impostiamo le porte di entrata 80 e 443)
    - "traefik.http.routers.portainer.tls=true" (attiviamo il certificato SSL) 