# HackLab
Pentesting/Hack &amp; autre trucs en local sous Hyper-V
________________________________
________________________________
## Prérequis :
- Windows 10/11 Pro
________________________________
________________________________
## Installation :
- Téléchargez [MediaCreationTool_22H2](https://go.microsoft.com/fwlink/?LinkId=2265055)
  - Choisissez "Créer un support d'installation
  - ...
- Téléchargez l'[iso Hyper-V Kali-Linux](https://cdimage.kali.org/kali-2024.1/kali-linux-2024.1-hyperv-amd64.7z)
- L'.ISO Ubuntu est intégré à Hyper-V
- Activez la fonctionalité Hyper-V :

[image]
________________________________
### Ubuntu Victim :
- Lancez le gestionaire Hyper-v
- Dans le gestionnaire :
- Cliquez sur "Création rapide"
- Puis
 
[image]

- Donnez lui un nom reconaissable : Ubuntu Victim
________________________________
### Windows 10 Victim :
- Séléctionnez "Source d'installation_locale"
- Cliquez "Modifier la source d'installation"
- Choisissez l'ISO Windows préalablement téléchargé

[image]
________________________________
### Kali-Linux :
-  Extrayez kali-linux-2024.1-hyperv-amd64.7z  
-  Retournez sur le gestionnaire Hyper-V
-  Cliquez sur "Création Rapide"
-  "Source d'installation_locale"
-  Décochez "Cet ordinateur virtuel va exécuter Windows"
-  Sélectionnez "Modifier la source d'installation"

[image]
________________________________
### Création Commutateur :
- Une fois vos machines crées et nommée allez dans le gestionnaire et seléctionnez "Gestionnaire de commutateur virtuel"
- Créez un nouveau "Commutateur virtuel externe"
- Nommez le "HLab"
- Cochez "Autorisez le system d'exploitation de gestion à partager cette carte réseau"
- "Appliquez" puis "OK"

[image]
________________________________
### Mise en réseau :
- Selectionnez une machines virtuelles
- Cliquez sur l'option "Paramètres"
- Puis "Carte réseau"
- Sélectionnez votre commutateur précédement créer
- Désactivez l'identification vlan
- "Appliquez" puis "OK"
- Réitérez avec les deux autres ordinateurs virtuels

[image]
________________________________
### Connexion aux machines & Maj :
- Double-cliquez sur la machine Kali-Linux et Ubuntu
- Une fenêtre s'ouvre, pressez "Démarrez"
- Connectez vous aux ordinateurs
- Mettez les à jour :
  - sudo apt-get update 
  - sudo apt-get upgrade
- Double-cliquez sur la machine Windows
- Mettez la à jour via Windows update
________________________________
### Customisez vos machine avec vos application préférée :
- Installez simplement vos application comme d'habitude
________________________________
### Passez en Local :
- Quittez vos machines virtuelles
- Retournez sur le gestionnaire Hyper-V
- Accedez à "Gestionnaire de commutateur virtuel"
- Allez sur "HLab" et changez le type de connexion en "privé"
Les Ordinateurs ne communiquerons plus qu'entre eux


