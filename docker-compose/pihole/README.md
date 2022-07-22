# Configurazione di pihole

Pihole come adblock sulla rete

### Parametri di configurazione
- configurazione pihole
    - configurazione delle porte (per mandare la configurazione ai dispositivi)
        - "53:53/tcp"
        - "53:53/udp"
    - configurazione del dns
        - 127.0.0.1 (per poter usare la connessione ad internet della macchina)
        - 1.1.1.1
- configurazione del timezone
    - TZ=Europe/Rome
- configurazione traefik
    - "traefik.enable=true" (attiviamo traefik)
    - "traefik.http.routers.pihole.rule=Host(`pihole.local`)" (impostiamo il dominio)
    - "traefik.http.services.pihole.loadbalancer.server.port=80" (impostiamo la porta)
    - "traefik.http.routers.pihole.entrypoints=web, websecure" (impostiamo le porte di entrata 80 e 443)
    - "traefik.http.routers.pihole.tls=true" (attiviamo il certificato SSL) 