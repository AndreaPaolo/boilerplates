# Configurazione di wireguard


###### Configurazione peer
- SERVERURL: indirizzo ip pubblico statico, un dns, se impostato su auto ricaverà lui l'indirizzo ip.
- PEERS: numero di configurazioni
- PEERDNS: se impostato su auto verrà usato il server dns di docker, se impostato sull'indirizzo ip interno di pihole verrà utilizzato quest'ultimo.

###### Configurazione del qrcode
> docker exec -it wireguard /app/show-peer 1 (numero del peer da mostrare) [fuori dal container]

> /app/show-peer 1 (numero del peer da mostrare) [dentro al container]