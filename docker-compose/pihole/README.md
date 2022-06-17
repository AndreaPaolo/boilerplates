# Configurazione di pihole

## Configurazione con traefik
Creazione di un container docker con pihole sotto il reverse proxy di traefik.
Esponiamo entrambi i container nello stesso network, tramite un dns manager sarà accessibile all'indirizzo "pihole.dominio". Reindirizzamento automatico https

### Errori dns 
sudo nano /etc/resolv.conf
nameserver 127.0.0.1