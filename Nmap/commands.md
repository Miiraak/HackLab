# Nmap : Commands & Trucs
## Commande basique :
### Scan basique des 1000 premiers ports :

    command: nmap <cible>

### Scan de port spécifiques :

    Command: nmap -p <num>-<num> <cible>
    
Tout les ports :

    Command: nmap -p- <cible>

Les X top ports :

    Command: nmap --top-ports <num> <cible>
_____________________
## Sauvegarde :

Sauvegarde les résultats sous format .txt

    Commande: nmap <options> <cible> -oN output.txt
Sauvegarde sous format XML

    Command: nmap <options> <cible> -oX output.xml
_____________________
## Commandes spécifiques :
### Scan UDP (-sU)

Scan les ports UDP ouverts de la cible (IP/hostName). Envoi un paquet UDP à chaque ports de la cible et attend une réponse. Il il recois un message d'erreur cela signifie que les ports sont fermé. Cependant si il n'y a aucune réponse, cela signifie que les ports sont ouvert.

    Commande : nmap -sU <cible>

### Scan FIN (-sF)

Ici la méthode envoie des Flag Fin. Du au firewall les paquest SYN peuvent être bloqués. Dans ce cas, le scan FIN by-pass le firewall.

    Command: nmap -sU <cible>

### Ping Scan (-sP)

Cette technique est seulement utilisée pour vérifier si l'host est disponible. Il ne détecte pas les ports ouverts. Il retourne aussi la MAC adresse. 

    Command: nmap -sP <cible>

### Scan TCP SYN (-sS)

Nmap envoie un paquet SYN à la cible, mais ne crée aucune session, cela a pour résultat d'empecher l'ordinateur cible de crée un log de l'interaction effectuée.

    Command: nmap -sS <cible>

### TCP Connect() Scan (-sT)

UNIX socket utilise un systme appelé connect() pour démarrer une connexion TCP.

    Command: nmap -sT <cible>

### Détection de version (-sV)

Cette technique est utilisée pour trouver les services spécifique utilisant les port ouvert, sa version et le nom du produit. Elle utilise un scan TCP SYN.

    Command: nmap -sV <cible>

### Scan Idle (-sI)

Un scan avancé qui n'envois aucun paquet depuis notre propre adresse IP, elle passe par un autre host du réseau de la cible pour envoyer de paquet.

    Command: nmap -sI <cible>

### Scan OS (-O)

Un scan complet des port ouvert, les services, la MAC adresse, le type de materiel, la version de l'OS, l'OS et des détails supplémentaires.

    Command: nmap -O <cible>
______________________


