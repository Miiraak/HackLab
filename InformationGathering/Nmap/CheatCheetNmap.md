# Nmap : CheatCheet
## Target Specification
### Scan Mono IP :

    nmap <host>

### Scan Multi IP :

    nmap <host> <host>
    
### Scan Range IP :

    nmap 192.168.1.1-254

### Scan Domain
```
    nmap [scanme.nmap.org]
```

Les X top ports :

    nmap --top-ports <num> <cible>

Outre passe la réolution DNS :

    nmap -n <cible> 
_____________________
## Nmap Scan Technique
```
-sS	nmap 192.168.1.1 -sS	TCP SYN port scan (Default)
-sT	nmap 192.168.1.1 -sT	TCP connect port scan (Default without root privilege)
-sU	nmap 192.168.1.1 -sU	UDP port scan
-sA	nmap 192.168.1.1 -sA	TCP ACK port scan
-sW	nmap 192.168.1.1 -sW	TCP Window port scan
-sM	nmap 192.168.1.1 -sM	TCP Maimon port scan
```
## Sauvegarde :

Sauvegarde les résultats sous format .txt

    nmap <options> <cible> -oN output.txt
Sauvegarde sous format XML

    nmap <options> <cible> -oX output.xml
_____________________
## Commandes spécifiques :
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
