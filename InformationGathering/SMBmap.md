# SMBmap 
Permet toute sorte de chose,

Affiche l'IP, l'adresse MAC, les disques logique, les permissions ainsi que les commentaire. (-H)

    smbmap -H <cible>

  ___________________________

Affiche le nom, le domaine et le system d'exploitation (-v)

    smbmap -v -H <cible>

  ____________________________

Execute une commande sur l'hote spécifié 

    smbmap H <cible> -p <x> -x ifconfig

  _____________________________

  Liste récusivement les dossier spécifiés

      smbmap -H <cible> -r

  _____________________________
