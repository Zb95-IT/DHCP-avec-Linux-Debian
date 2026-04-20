# TP DHCP Debian

## Objectif
Configurer un serveur DHCP sur Debian pour distribuer des adresses sur le réseau `172.20.0.0/24`.

## Configuration réalisée
- Serveur Debian en IP statique : `172.20.0.1/24`
- Étendue DHCP : `172.20.0.80` à `172.20.0.150`
- Réservation MAC pour le client 2 : `172.20.0.100`

## Captures

### 1. Configuration du serveur DHCP
On voit dans le fichier `dhcpd.conf` :
- la plage d’adresses DHCP
- la réservation du client 2 en `172.20.0.100`

![Configuration DHCP du serveur](images/01-serveur-dhcp.png)

### 2. Configuration IP du client 1
Le client 1 est en DHCP et reçoit une adresse dans la plage du serveur.

![Client 1](images/02-client1.png)

### 3. Configuration IP du client 2
Le client 2 est en DHCP et reçoit bien l’adresse réservée `172.20.0.100`.

![Client 2](images/03-client2.png)

### 4. Baux DHCP sur le serveur
On voit les baux attribués par le serveur DHCP.

![Baux DHCP](images/04-baux-dhcp.png)
