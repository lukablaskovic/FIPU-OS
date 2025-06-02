### _FIPU: os-final_ - Službeni šalabahter

**Upravljanje paketima**

```bash
→ apt update # ažuriranje popisa paketa
→ apt upgrade # nadogradnja instaliranih paketa
→ apt install <package_1> <package_2>
→ apt remove <package> # uklanjanje paketa
→ apt purge <package> # uklanjanje paketa i konfiguracijskih datoteka
→ apt autoremove <package> # uklanjanje paketa i njegovih zavisnosti
→ apt search <search_term> # pretraga paketa
→ apt list # popis svih paketa (Zastavice: --installed, --upgradable)
```

**Upravljanje procesima**

```bash
→ ps aux # popis svih procesa
→ top/htop # interaktivni pregled procesa
→ kill <PID> # zaustavlja proces po PID-u
→ killall <command> # zaustavljanje svih procesa, potprocesa i dretvi
→ pkill <command> # zaustavlja proces prema točnoj naredbi
→ pidof <command> # vraća PID prema točnoj naredbi
→ pgrep <command_subset> # vraća PID prema regularnom izrazu
# Zastavice kill: -9 (sigkill), -15 (sigterm), -1 (sighup), -2 (sigint), -19 (sigstop), -18 (sigcont)

# Upravljanje prioritetom
nice -n <prioritet> <command> # pokretanje datoteke sa zadanim prioritetom
renice <prioritet> -p <PID> # promjena prioriteta pokrenutog procesa
ALT/OPT + ←→ # promjena terminal sesije
```

**Upravljanje korisnicima i grupama**

```bash
→ who, whoami # informacije o korisnicima i grupama
→ id <korisnik> # informacije o korisniku
→ groups <korisnik> # popis grupa korisnika
→ su - <korisnik> # prijava kao drugi korisnik
→ logout # odjava trenutnog korisnika - lokalni terminal
→ exit # odjava trenutnog korisnika - SSH terminal

# upravljanje korisnicima
→ useradd [opcije/zastavice] <username>
→ usermod [opcije/zastavice] <username>
# Zastavice: -a, -G, -g, -d, -m, -s, -l, -L, -U, -e, -c
→ userdel [opcije/zastavice] <username>
# Zastavice: -r, -f

# Dodavanje grupe
→ groupadd <groupname>

# Upravljanje dozvolama
→ chmod <octal_permission> <path_abs_rel> # promjena dozvole datoteke
→ chown <owner>:<group> <path_abs_rel> # promjena vlasnika/grupe datoteke
```

**Preusmjeravanje (piping)**

```bash
→ naredba_1 | naredba_2 | naredba_3 # preusmjeravanje izlaza jedne naredbe u ulaz druge
→ naredba_1 > datoteka # preusmjeravanje izlaza u datoteku
→ naredba_1 >> datoteka # dodavanje izlaza na kraj datoteke (append)
```

**Upravljanje servisima**

```bash
→ systemctl status <service> # status servisa
→ systemctl start <service> # pokretanje servisa
→ systemctl stop <service> # zaustavljanje servisa
→ systemctl restart <service> # ponovno pokretanje servisa
→ systemctl enable <service> # omogućavanje servisa pri pokretanju sustava
→ systemctl disable <service> # onemogućavanje servisa pri pokretanju sustava

→ lsof -i :<port> # popis procesa koji koriste određeni port
→ ip address # popis mrežnih sučelja i njihovih IP adresa
→ hostname -I # ispis IP adrese mrežnog sučelja
→ ss # zastavica -t (TCP), -u (UDP), -l (listening), -p (proces koji koristi port), -n (numerički prikaz)

→ ssh <username>@<host_ip> # SSH povezivanje preko hosta (Bridged)
→ ssh <username>@<host_ip> -p <port> # SSH povezivanje preko porta (NAT sa port forwardingom)
```

**Putanje čestih konfiguracijskih datoteka**

```bash
/bin/bash # putanja do bash shella
~/.bashrc # konfiguracija bash shella
~/.ssh/rc # konfiguracija SSH sesije
/etc/passwd	 # popis korisnika i njihovih informacija
/etc/group # popis grupa i njihovih članova
/etc/shadow # sigurnosne informacije o korisnicima (lozinke, itd.)
/etc/gshadow # sigurnosne informacije o grupama
~/.nanorc # konfiguracija nano uređivača
~/.vimrc # konfiguracija vim uređivača

→ source <path_abs_rel> # ažuriranje konfiguracijske datoteke u trenutnoj sesiji
```

<footer style="float:right;">
    <i>FIPU: os-final</i> - Službeni šalabahter (11. 6. 2025.)
</footer>
