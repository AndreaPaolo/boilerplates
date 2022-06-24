# Configurazione di authelia
Middleware di traefik che aggiunge un login

###E' richiesta l'applicazione Authenticator

###### Redirect 
Redirect alla schermata di login
- 'traefik.http.middlewares.authelia.forwardauth.address=http://authelia:9091/api/verify?rd=https://dominio'
- 'traefik.http.middlewares.authelia.forwardauth.trustForwardHeader=true'
- 'traefik.http.middlewares.authelia.forwardauth.authResponseHeaders=Remote-User,Remote-Groups,Remote-Name,Remote-Email'

###### Come inserirlo nelle configurazioni
> "traefik.http.routers.servizio.middlewares=authelia@docker" 

###### File di configurazione
- Il salvataggio degli utenti può avvenire su file o su database.
- Notifiche tramite email (server smtp) o tramite file

###### Salvataggio utenti su file
La password deve essere criptata tramire il comando. La email è obbligatoria.
> docker run authelia/authelia:latest authelia hash-password passwordhere