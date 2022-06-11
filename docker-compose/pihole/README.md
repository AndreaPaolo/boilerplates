# Configurazione di pihole

## Configurazione standard
Creazione di un container docker con pihole, accessibile all'indirizzo ip della macchina alla porta 80

## Configurazione con traefik
Creazione di un container docker con pihole sotto il reverse proxy di traefik.
Esponiamo entrambi i container nello stesso network, tramite un dns manager sarà accessibile all'indirizzo "pihole.dominio".