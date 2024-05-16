# Guide HackLab : Windows 10/11

Nous installerons une machine virtuel Kali-Linux et un second PC "Victime" qui nous permettera de tester toute sorte de choses en toute légalité sans compromettre notre sécurité et sans dépenser le moindre centime.

Nous créerons aussi un "réseau NAT" pour permettre aux deux ordinateurs de se communiquer l'un avec l'autre ainsi qu'un "réseau par pont" pour le Kali-Linux, pour les accès aux data-base, mise à jour, installation de paquet, fetch etc...
## Requis :
- VirtualBox comme virtualisateur, un logiciel de libre de virtualisation, tournant sur Windows, MacOS et Linux.
- L'OS Kali-Linux pour notre PC d'attaque. 
- Un OS Ubuntu intentionnellement vulnérable conçu par [Rapid7](https://www.rapid7.com/).
---
## Téléchargement / Installation
#### VirtualBox :
- Télécharger l'executable windows [VirtualBox](https://www.virtualbox.org/wiki/Downloads) 
- Lancer l'exécutable et suivez la procédure standard d'installation.
#### Kali-Linux :
- Téléchargez l'ISO de Kali [ici](https://cdimage.kali.org/kali-2024.1/kali-linux-2024.1-virtualbox-amd64.7z)
#### Metaploitable 2 :
- Téléchargez l'ISO Metasploitable [ici](https://sourceforge.net/projects/metasploitable/)

## Création des VM :
- Allez dans C:/Utilisateurs/[...]/VirtualBox VMs
- Créez un dossier ISO et extrayez vos ISO compressée à l'intérieur.
- Lancez VirtualBox

### Kali-Linux
- Appuyez sur "Nouvelle"
  ```
  Nom:         Kali-Linux
  Folder:      C:\Users\...\VirtualBox VMs
  ISO image:   <non sélectionné>
  Edition:     -
  Type:        Linux
  Version:     Debian (64-bit) (Other Linux (64-bit) si vous avez une machine avec peu de RAM)
  ```
- Suivant > Suivant > Suivant > Finish
---
### Metasploitable
- Appuyez sur "Nouvelle"
  ```
  Nom:         Metasploitable
  Folder:      C:\Users\...\VirtualBox VMs
  ISO image:   <non sélectionné>
  Edition:     -
  Type:        Linux
  Version:     Other Linux (64-bit)
  ```
- Suivant > Suivant > Suivant > Finish

---
## Paramétrage :
- Cliquez sur les trois barres horizontales
- Allez sur "Réseau"
- Puis dans l'onglet NAT Network
- Créer
- Sous "Général Options"
  ```
  Nom:           DangerousNetWork
  IPv4 Prefix:   6.6.6.0/24
  
  ☑️ Enable DHCP
  ❎ Enable IPv6
  ```

### Kali-Linux
#### Stockage :
- Cliquez sur configuration
- Stockage
- Supprimez le kali-Linux.vdi
- Selectionnez kali-linux.vdi que vous avez téléchargé.
#### Réseau :
- Allez sous "Réseau"
  ```
  Adapter 1
  
  ☑️ Activer interface réseau
  
  Mode d'accès réseau:   Accès par pont
  Name :                 [Votre carte réseau]
  ```
  ```
  Adapter 2
  
  ☑️ Activer interface réseau
  
  Mode d'accès réseau:   Réseau NAT
  Nom :                  DangerousNetWork
  ```
  - OK
  - Démarrez
  - 
  

### Metasploitable
#### Stockage :
- Cliquez sur configuration
- Stockage
- Supprimez le Metasploitable.vdi
- Selectionnez le Metasploitable.vmdk que vous avez téléchargé.
- ## Réseau :
- Allez sous "Réseau"
  ```
  Adapter 1
  
  ☑️ Activer interface réseau

  Mode d'accès réseau:   Réseau NAT
  Nom :                  DangerousNetWork
  ```
- OK
- Démarrez
- Attendez qu'elle finisse de s'initaliser
  ```
  Login    :   msfadmin
  Password :   msfadmin
  ```
- C'est tout, elle est exploitable

---
