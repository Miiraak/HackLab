# Outil de reconnaissance ARP (actif/passif)

Pour analyser le réseau de votre ordinateur. Dans un range défini (-r)

    netdiscover -r 192.168.1.0/24

Ou une IP spécifique (-r):

    netdiscover -r <cible>
_________________________

Pour une analyse discrète nous pouvons passer en reconnaissance passive (-p)

    netdiscover -p -r <cible>/subnet

__________________________

