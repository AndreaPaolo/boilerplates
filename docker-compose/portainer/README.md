# Configurazione di portainer

## Configurazione con traefik
Creazione di un container docker con portainer sotto il reverse proxy di traefik.
Esponiamo entrambi i container nello stesso network, tramite un dns manager sarà accessibile all'indirizzo "portainer.dominio". Reindirizzamento automatico https

###### Volumi
- "/var/run/docker.sock" => Ci mettiamo in ascolto sul socket di docker così da avere sincronizzati tutti i container 
- "portainer_data" => Storage dei dati di portainer