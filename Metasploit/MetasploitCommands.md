### Metasploit :

```
Commandes:                      Description :
____________________            ____________________________
search [regex]                  Recherche de module

use exploit/[ExploitPath]       Choisir un exploit à utilliser

set PAYLOAD [PayloadPath]       Choisir un Payload à utiliser

show options                    Affiche ls options pour le module actuel

set [Option] [Value]            Paramétrage des options

msf > exploit                   Lancez exploit seléctionné 

```
---
#### Mode Auxiliaire utiles
###### Port Scanner:
```
use auxiliary/scanner/portscan/tcp
set RHOSTS x.x.x.0/24
run
```

###### Énumération DNS:
```
msf > use auxiliary/gather/dns_enum
msf > set DOMAIN target.tgt
msf > run
```

###### Serveur FTP:
```
msf > use auxiliary/server/ftp
msf > set FTPROOT /tmp/ftproot
msf > run
```

###### Serveur Proxy:
```
msf > use auxiliary/server/socks4
msf > run 
```
---

### Misc Commands:
```
idletime:                                    Affiche depuis combien de temps le GUI de la cible est en idle.

uictl [enable/disable] [keyboard/mouse]:     Active/Desactive le clavier et/ou la souris de la cible.

screenshot:                                  Effectue et enregistre un screenshot de la machine ciblée.
```
---
##### Managing Sessions

###### Multiple Exploitation: 

Run the exploit expecting a single session that is immediately backgrounded:

```
msf > exploit -z
```

Run the exploit in the background expecting one or more sessions that are immediately backgrounded:

```
msf > exploit –j
```

###### List all current jobs (usually exploit listeners):

```
msf > jobs –l
```

###### Kill a job:

```
msf > jobs –k [JobID]
```

##### Multiple Sessions:

###### List all backgrounded sessions:

```
msf > sessions -l
```

###### Interact with a backgrounded session:

```
msf > session -i [SessionID]
```
