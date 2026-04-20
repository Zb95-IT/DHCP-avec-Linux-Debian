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

<img width="362" height="302" alt="580956051-3d218ad3-10fe-4ac0-92fa-8b502ad24416 (1)" src="https://github.com/user-attachments/assets/a3c37ab2-4dba-4e3f-b97e-30f039f509d1" />


### 2. Configuration IP du client 1
Le client 1 est en DHCP et reçoit une adresse dans la plage du serveur.

<img width="1043" height="140" alt="3068986c-d690-484b-8336-0a67c328a16c" src="https://github.com/user-attachments/assets/3761aa65-b9fd-4caf-bb1f-f5b60a74ebc8" />


### 3. Configuration IP du client 2
Le client 2 est en DHCP et reçoit bien l’adresse réservée `172.20.0.100`.

<img width="1014" height="177" alt="79bb15f3-59ba-4aac-b64a-ec83adb224aa" src="https://github.com/user-attachments/assets/77b780f8-441b-4397-88a0-3f5ef9d2d978" />


### 4. Baux DHCP sur le serveur
On voit les baux attribués par le serveur DHCP.

<img width="588" height="662" alt="c7d79507-8b32-4975-b4a3-8983e0e40ba9" src="https://github.com/user-attachments/assets/3142cf9f-0497-4052-a46d-ad7d49c02798" />

