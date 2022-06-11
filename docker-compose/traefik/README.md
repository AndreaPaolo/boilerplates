# Configurazione di traefik

## Configurazione standard
Creazione di un container docker con traefik come reverse proxy, accessibile all'indirizzo ip della macchina alla porta 8080

###### Volumi
- "/path/traefik:/etc/traefik" => configurazione traefik
- "/var/run/docker.sock:/var/run/docker.sock:ro" => gestione dei container 