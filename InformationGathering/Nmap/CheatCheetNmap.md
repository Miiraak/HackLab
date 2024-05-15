# Nmap : CheatCheet
## Target Specification
```
EXAMPLE	:              DESCRIPTION :
nmap <host>            Simple IP Scan
nmap <host> <host>     Multi IP Scan
nmap <host>-245        Range IP Scan
nmap <domain>          Domain Scan
```

## Nmap Scan Technique
```
SWITCH:     EXAMPLE :	                DESCRIPTION :
-sS	    nmap 192.168.1.1 -sS	TCP SYN port scan (Default)
-sT	    nmap 192.168.1.1 -sT	TCP connect port scan (Default without root privilege)
-sU	    nmap 192.168.1.1 -sU	UDP port scan
-sA	    nmap 192.168.1.1 -sA	TCP ACK port scan
-sW	    nmap 192.168.1.1 -sW	TCP Window port scan
-sM	    nmap 192.168.1.1 -sM	TCP Maimon port scan
```
## Host Discovery :
```
SWITCH :    EXAMPLE	:                       DESCRIPTION :
-sL	    nmap 192.168.1.1-3 -sL	        No Scan. List targets only
-sn	    nmap 192.168.1.1/24 -sn	        Disable port scanning. Host discovery only.
-Pn	    nmap 192.168.1.1-5 -Pn	        Disable host discovery. Port scan only.
-PS	    nmap 192.168.1.1-5 -PS22-25,80	TCP SYN discovery on port x. Port 80 by default
-PA	    nmap 192.168.1.1-5 -PA22-25,80	TCP ACK discovery on port x. Port 80 by default
-PU	    nmap 192.168.1.1-5 -PU53	        UDP discovery on port x. Port 40125 by default
-PR	    nmap 192.168.1.1-1/24 -PR	        ARP discovery on local network
-n	    nmap 192.168.1.1 -n	                Never do DNS resolution
```

Sauvegarde les résultats sous format .txt

    nmap <options> <cible> -oN output.txt
Sauvegarde sous format XML

    nmap <options> <cible> -oX output.xml

_____________________
## Commandes spécifiques :

### Outre passe la réolution DNS :

    nmap -n <cible> 
    
### Scan UDP (-sU)

Scan les ports UDP ouverts de la cible (IP/hostName). Envoi un paquet UDP à chaque ports de la cible et attend une réponse. Il il recois un message d'erreur cela signifie que les ports sont fermé. Cependant si il n'y a aucune réponse, cela signifie que les ports sont ouvert.

    nmap -sU <cible>

### Scan FIN (-sF)

Ici la méthode envoie des Flag Fin. Du au firewall les paquest SYN peuvent être bloqués. Dans ce cas, le scan FIN by-pass le firewall.

    nmap -sU <cible>

### Ping Scan (-sP)

Cette technique est seulement utilisée pour vérifier si l'host est disponible. Il ne détecte pas les ports ouverts. Il retourne aussi la MAC adresse. 

    nmap -sP <cible>

### Scan TCP SYN (-sS)

Nmap envoie un paquet SYN à la cible, mais ne crée aucune session, cela a pour résultat d'empecher l'ordinateur cible de crée un log de l'interaction effectuée.

    nmap -sS <cible>

### Scan TCP Connect() (-sT)

UNIX socket utilise un systme appelé connect() pour démarrer une connexion TCP.

    nmap -sT <cible>

### Détection de version (-sV)

Cette technique est utilisée pour trouver les services spécifique utilisant les port ouvert, sa version et le nom du produit. Elle utilise un scan TCP SYN.

    nmap -sV <cible>

### Scan Idle (-sI)

Un scan avancé qui n'envois aucun paquet depuis notre propre adresse IP, elle passe par un autre host du réseau de la cible pour envoyer de paquet.

    nmap -sI <cible>

### Scan All (-A)

Un scan super agressif qui effectue un scan OS (version, scan script, traceroute...)

    nmap -A <tier> <cible>

### Scan OS (-O)

Un scan complet des port ouvert, les services, la MAC adresse, le type de materiel, la version de l'OS, l'OS et des détails supplémentaires.

    nmap -O <cible>
______________________
