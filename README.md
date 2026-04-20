[README_TP_DHCP_Debian.md](https://github.com/user-attachments/files/26905868/README_TP_DHCP_Debian.md)

# TP DHCP Server sur Debian

## Objectif
Mise en place d’un serveur DHCP sur une VM Debian avec :

- une interface serveur en IP statique : `172.20.0.1/24`
- une étendue DHCP : `172.20.0.80` à `172.20.0.150`
- un client 1 recevant une adresse IP en DHCP dans la plage
- un client 2 recevant une adresse réservée : `172.20.0.100`
- vérification des baux côté serveur

---

## 1. Configuration du serveur DHCP

Cette capture montre la configuration du fichier `dhcpd.conf` sur le serveur Debian.  
On y voit :

- l’étendue DHCP sur le réseau `172.20.0.0/24`
- la plage dynamique `172.20.0.80` à `172.20.0.99` puis `172.20.0.101` à `172.20.0.150`
- la réservation MAC du client 2 avec l’adresse fixe `172.20.0.100`

![Configuration DHCP du serveur](images/01-configuration-dhcp-serveur.png)

---

## 2. Configuration IP du client 1

Cette capture montre que le client 1 est bien configuré en DHCP et qu’il a reçu automatiquement une adresse IP dans la plage du serveur DHCP.  
Adresse obtenue : `172.20.0.81/24`.

![Adresse IP du client 1](images/02-client1-dhcp.png)

---

## 3. Configuration IP du client 2 avec réservation

Cette capture montre que le client 2 reçoit bien l’adresse IP réservée `172.20.0.100/24` grâce à la réservation MAC configurée sur le serveur DHCP.

![Adresse IP du client 2 avec réservation](images/03-client2-reservation.png)

---

## 4. Vérification des baux DHCP sur le serveur

Cette capture montre le contenu du fichier des baux DHCP sur le serveur Debian.  
Elle permet de vérifier les adresses distribuées aux clients par le service DHCP.

![Baux DHCP sur le serveur](images/04-baux-dhcp.png)

---

## Résultat

Le serveur DHCP fonctionne correctement :

- le serveur Debian possède une configuration IP statique correcte
- le service DHCP distribue des adresses dans la plage attendue
- le client 1 reçoit bien une adresse IP dynamique
- le client 2 reçoit bien l’adresse réservée `172.20.0.100`
- les baux DHCP sont visibles sur le serveur

---

## Arborescence conseillée du dépôt

```text
README.md
images/
├── 01-configuration-dhcp-serveur.png
├── 02-client1-dhcp.png
├── 03-client2-reservation.png
└── 04-baux-dhcp.png
```
