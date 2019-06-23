# Projet-InfraSI
  
 SSH hboueix@192.168.56.111 -D 7777 (port) + CONFIG sur firefox pour rediriger la navigation vers la VM client
 
## OS & Matériel :
 
 + Routeur pfSense 2.4.4
 + Machines clients CentOS 7 minimal
 + OpenVswitch
 
## Schéma 
  
<p align="center">
  <img src="./images/schema.PNG" title="Schéma">
</p>
 
## Installation de pfSense

Tout d'abord :  
  
1) Démarrer la machine avec le support d'installation inseré
2) Laisser l'autoboot (par défaut)
3) Accepter: "Copyright & Distribution"
4) Selectionner: "Install pfSense"
5) Selectionner: "French keymap" & "Continue"
6) Partitioning: "Auto(UFS)"
7) Manual Config: "No"
8) Reboot et éjecter le support d'installation 
  

## Configuration basique de pfSense

Après le reboot on arrive donc sur l'écran de menu. On va effectuer une configuration basique pour l'instant, celle-ci nous permettra d'accèder à l'interface web d'administration.   
  
1) Option 1 : Assign Interfaces
    - Définir VLANs maintenant ? : "n"
    - Renseigner interface WAN (em0) et l'interface LAN (em1)
    - Valider : "y"
2) Option 2 : Set Interface(s) IP address
    - Selectionner l'interface WAN
    - DHCPv4 ? : "y"
    - DHCPv6 ? : "n"
    - <Enter> pour pas d'IPv6
    - Revert to HTTP ? : "n"
    - <Enter> pour continuer  
3) Option 2 : Set Interface(s) IP address
    - Select l'interface LAN
    - Entrez l'adresse IPV4 : 192.168.1.1
    - Entrez le masque au format CIDR : 24
    - <Enter> pour pas de gateway
    - <Enter> pour pas d'IPv6
    - DHCP server ? : "y"
    - Adress range : 192.168.1.10 - 192.168.1.150
    - Revert to HTTP ? "no"
    - <Enter> pour continuer
  
Nous pouvons désormais accèder à l'interface web d'administration depuis le LAN à l'adresse `192.168.1.1`.  
  
Lors de la première connexion, vous serez guider pour une première "configuration".

1) Suivre le setup
2) Général Information :
    - Renseigner hostname, domain et DNS
    - Laisser cocher "Override DNS"
3) Régler la localisation et l'heure
4) Configurer l'interface WAN
5) Configurer l'interface LAN
5) Modifier le mdp admin (qui est également le mdp de la machine root)
6) Reload & Finish  
  
Normalement avec le schéma et la configuration actuelle, toutes les machines devraient pouvoir se ping et accèder à Internet.  
  
De plus toutes les machines ont accès au serveur DNS du routeur, et ce dernier récupère les serveurs DNS du WAN (grâce à l'option "Override DNS").







      
  
  
  
  
  
  
  
  
  
  
  
  
 
  





