# Configurazione di wireguard
Self hosted vpn

### Parametri di configurazione
- configurazione permessi
    - PGID=1000 (si trovano scrivendo `id` nel terminale della macchina)
    - PUID=1000
- configurazione del timezone
    - TZ=Europe/Rome
- configurazione vpn
      - SERVERURL=auto (auto trova direttamente l'ip pubblico)
      - SERVERPORT=51820 (porta del servizio)
      - PEERS=1 (numero di configurazioni)
      - PEERDNS=172.21.0.3 (indirizzo del dns, se si usa pihole va inserito l'ip del container)
      - INTERNAL_SUBNET=10.13.13.0 (indizzo ip della configurazione)
      - ALLOWEDIPS=0.0.0.0/0
      - LOG_CONFS=true
- configurazione traefik
    - "traefik.enable=true"
    - "traefik.udp.routers.wireguard.entrypoints=wireguard"
    - "traefik.udp.routers.wireguard.service=wireguard"
    - "traefik.udp.services.wireguard.loadbalancer.server.port=51820"

### Comandi per trovare il qrcode di configurazione
> docker exec -it wireguard /app/show-peer 1 (numero del peer da mostrare) [fuori dal container]

> /app/show-peer 1 (numero del peer da mostrare) [dentro al container]