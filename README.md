# Projet-InfraSI
  
 SSH hboueix@192.168.56.111 -D 7777 (port) + CONFIG sur firefox pour rediriger la navigation vers la VM client
 
 ## OS utilisés
 
 + pfSense
 + CentOS 7 minimal
 + Ubuntu 18.04.2 Desktop
 
 ## Matériel
 
 + Poste client(s)
 + Serveur(s)
 + Machine routeur
 
 ## SHEMA
 
 ## Installation pfSense
 
  1) Démarrer la machine avec sup.install insseré
  2) Laisser l'autoboot (par défault)
  3) Accepter: "Copyright & Distribution"
  4) Selectionner: "Install pfSense"
  5) Selectionner: "French keymap" & " continue "
  6) Partitioning: "Auto(UFS)"
  7) Manual Config: "No"
  8) Reboot et éjécter le supp-install
  
  ## Configuration de pfSense
   ### Option 1 : Assigner Interfaces
      1) Définir VLANs now ? : NON
      2) Renseigner interface WAN (em0) AND interface LAN (em0)
      3) Valider : "y"
    
   ### Option 2 : Set Int-IP Add
      1) Select int-WAN
      2) DHCP4? : "y"
      3) DHCP6? : "n"
      4) "Enter" for none IPv6
      5) Revert to HTTP ? "n"
      6) <Enter> continue
   ### Option 2 : Set Int-IP Add
      1) Select int-LAN
      2) Entrez l'adresse IPV4 : 192.168.1.1
      3) Subnet masks CIDR : 24
      4) gateway none
      5) IPv6 none
      6) DHCP server or LAN : choisir DHCP et appuyer sur "entrer"
      7) adress range : 192.168.1.10 to 192.168.1.145
      8) HTTP ? "no"
      9)<Enter> continue
      
  ## Configuration WEB BASIC (ADMIN)
     
    Sur le poste client du LAN (dans l'url d'un navigateur) : taper l'adresse IP
    
    1) Suivre le setup
    2) Général Information :
        hostname,domain,DNS
        Laisser cocher "Override DNS"
    3) Régler la localisation et l'heure
    4) Configure WAN interface :
          IP Adress -> l'adresse IP du Client
          Subnet masks : 24
    5) Modifier le mdp admin (qui est également le mdp de la machine root)
    6) Reload & finish
          
      
      
      
      
      
      
  
  
  
  
  
  
  
  
  
  
  
  
 
  





