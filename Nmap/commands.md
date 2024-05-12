_____________________
### Scan UDP (-sU)

Scan les ports UDP ouverts de la cible (IP/hostName). Envoi un paquet UDP à chaque ports de la cible et attend une réponse. Il il recois un message d'erreur cela signifie que les ports sont fermé. Cependant si il n'y a aucune réponse, cela signifie que les ports sont ouvert.

    Commande : nmap -sU <cible>
_____________________
### Scan FIN (-sF)

Ici la méthode envoie des Flag Fin. Du au firewall les paquest SYN peuvent être bloqués. Dans ce cas, le scan FIN by-pass le firewall.

    Command: nmap -sU <cible>
____________________
### Ping Scan (-sP)

Cette technique est seulement utilisée pour vérifier si l'host est disponible. Il ne détecte pas les ports ouverts. Il retourne aussi la MAC adresse. 

    Command: nmap -sP <cible>
____________________
### Scan TCP SYN (-sS)

Nmap envoie un paquet SYN à la cible, mais ne crée aucune session, cela a pour résultat d'empecher l'ordinateur cible de crée un log de l'interaction effectuée.

    Command: nmap -sS <cible>
____________________
### TCP Connect() Scan (-sT)

UNIX socket utilise un systme appelé connect() pour démarrer une connexion TCP.

    Command: nmap -sT <cible>
____________________
### Détection de version (-sV)

Cette technique est utilisée pour trouver les services spécifique utilisant les port ouvert, sa version et le nom du produit. Elle utilise un scan TCP SYN.

    Command: nmap -sV <cible>
_____________________
### Scan Idle (-sI)

Un scan avancé qui n'envois aucun paquet depuis notre propre adresse IP, elle passe par un autre host du réseau de la cible pour envoyer de paquet.

    Command: nmap -sI <cible>
_____________________
### Scan OS (-O)

Un scan complet des port ouvert, les services, la MAC adresse, le type de materiel, la version de l'OS, l'OS et des détails supplémentaires.

    Command: nmap -O <cible>
______________________


