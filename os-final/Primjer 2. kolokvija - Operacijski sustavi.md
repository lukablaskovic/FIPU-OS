# Primjer 2. kolokvija - Operacijski sustavi

**Nositelj**: doc. dr. sc. Ivan Lorencin
**Asistent**: Luka Blašković, mag. inf.

**Ustanova**: Sveučilište Jurja Dobrile u Puli, Fakultet informatike u Puli

<img src="https://raw.githubusercontent.com/lukablaskovic/FIPU-PJS/main/0.%20Template/FIPU_UNIPU.png" style="width:40%; box-shadow: none !important; float:left;"></img>

**Maksimalni broj bodova**: 50

**Rok za rješavanje**: 120 minuta

## Upute za predaju

Za kraju svakog zadatka je naglašeno što je potrebno predati za taj zadatak. Na Google Forms predajete zip datoteku koja komprimira sve datoteke (`rjesenje_X.txt`, `screenshot_X.png`, ...).

Primjer strukture koju mora obuhvaćati zip datoteka:

```
2_kolokvij/
├── rjesenje_1.txt
├── screenshot_1.png
├── screenshot_2.png
├── rjesenje_2.txt
├── screenshot_3.png
├── screenshot_4.png
├── rjesenje_3.txt
├── screenshot_5.png
├── screenshot_6.png
├── screenshot_7.png
├── rjesenje_4.txt
├── rjesenje_5.txt
├── screenshot_8.png
├── screenshot_9.png
└── screenshot_10.png
```

Navedene datoteke pohranjujete/uređujete **lokalno na vašem računalu** (ne u VM-u!).

<div style="page-break-after: always; break-after: page;"></div>


### 1. Zadatak (10 bodova)

Naredba `cp` služi za kopiranje datoteka iz jednog direktorija u drugi. Međutim, kada se spajamo na udaljeni poslužitelj, često postoji potreba za kopiranjem datoteka s direktorija na lokalnom u datotečni sustav na udaljenom sustavu. U tom slučaju možemo kombinirati naredbu `cp` sa `ssh` protokolom i "dobivamo" naredbu `scp` (_secure copy protocol_). `scp` je naredba koja omogućuje sigurno kopiranje datoteka između lokalnog i udaljenog sustava koristeći `SSH` protokol za samo spajanje.

_Sintaksa:_

```bash
scp [zastavice] <izvor> <korisnik_username>@<IP_adresa>:<putanja_na_poslužitelju>
```

Što se tiče `scp` zastavica, vrijede iste kao i za `cp` naredbu.

Zadatak je podignuti `OpenSSH` poslužitelj na `Ubuntu Serveru` i provjeriti konekciju prema danom poslužitelju - odaberite jedan od načina spajanja, a drugi način objasnite pismeno kako realizirati.

Napišite naredbe za sljedeće provjere na VM-u:

- kako ćete dokazati na kojem portu radi SSH servis?
- kako ćete provjeriti status SSH servisa?
- kako ćete restartati SSH servis?

Jednom kad ste se uspješno povezali, odaberite jednu datoteku/direktorij koji se nalazi na vašem lokalnom sustavu (npr. slika, PDF dokument, Word dokument, neki direktorij i sl.) i `scp` naredbom ju kopirajte u vaš `home` direktorij na VM-u.

**Za ovaj zadatak predajete**:

- `rjesenje_1.txt` - ručno upišite sve korištene naredbe (lokalne + VM) i objašnjenja ako postoje
- `screenshot_1.png` - snimka zaslona koja prikazuje uspješnu konekciju u lokalnom terminalu
- `screenshot_2.png` - snimka zaslona koja prikazuje uspješno kopiranu datoteku/direktorij na Ubuntu Serveru

### 2. Zadatak (7 bodova)

Na Ubuntu Serveru ažurirajte lokalnu bazu paketa i njihovih verzija. Nakon toga, izlistajte u terminal sve pakete koji se mogu ažurirati na noviju verziju, te ih naposljetku i ažurirajte.

Instalirajte paket `speedtest-cli` koji služi za testiranje brzine internetske veze preko Speedtest.net servisa. Provjerite ispravnost alata pozivanjem iste naredbe.

U jednoj naredbi, preusmjerite izlaz naredbe `speedtest-cli` u datoteku `/home/<vaš_username>/brzina_neta.txt`.

Kako ćete provjeriti sadržaj te datoteke na barem 2 načina?

Izmijenite dozvolu datoteke `brzina_neta.txt` tako da je samo vlasnik može čitati i pisati, grupa i ostali korisnici ne smiju imati nikakve dozvole. Napišite kako ste izračunali oktalnu reprezentaciju te dozvole.

**Za ovaj zadatak predajete:**

- `rjesenje_2.txt` - ručno upišite sve korištene naredbe i objašnjenja ako postoje
- `screenshot_3.png` - snimka zaslona koja prikazuje uspješno ažuriranje i instalaciju paketa
- `screenshot_4.png` - snimka zaslona koja prikazuje sadržaj datoteke `brzina_neta.txt` i izmijenjenu dozvolu

### 3. Zadatak (15 bodova)

Na Ubuntu Serveru napišite bash skriptu `timer.sh` koja će primati jedan argument - `broj_sekundi`. Skripta treba iterirati od `broj_sekundi` prema `0` i nakon svake iteracije ispisati: `"Preostalo N sec"`, npr. `"Preostalo 5 sec"`. Krajem svake iteracije pauzirajte izvođenje 1 sekundu (naredba `sleep`).

Napravite novu grupu korisnika `studenti` i jednog novog korisnika. Napišite naredbu koja će stvoriti novog korisnika sa zadanim home direktorijem, primarnom grupom `studenti` i `bash`-om kao zadanim _shellom_.

Dodijelite korisniku novu lozinku koja će biti današnji datum.

Kako ćete provjeriti pripadnost korisnika grupi `studenti`? Napišite barem 2 načina.

Definirajte dozvolu za datoteku `timer.sh` tako da je samo vlasnik može čitati, pisati i izvršavati, dok studenti mogu samo čitati i izvršavati, a ostali korisnici nemaju nikakve dozvole. Izmijenite grupu datoteke na grupu `studenti`, a vlasnik ostajete vi.

Provjerite zadanu dozvolu na način da se prijavite kao novi korisnik i pokušate izmijeniti sadržaj skripte.

**Za ovaj zadatak predajete**:

- `rjesenje_3.txt` - ručno upišite sve korištene naredbe i objašnjenja ako postoje
- `screenshot_5.png` - snimka zaslona koja prikazuje sadržaj skripte `timer.sh`
- `screenshot_6.png` - snimka zaslona koja prikazuje neuspješno izmjenjivanje skripte gdje ste autentificirani kao novi korisnik
- `screenshot_7.png` - snimka zaslona koja prikazuje podatke o novom korisniku unutar datoteke `/etc/passwd`

### 4. Zadatak (6 bodova)

Za sljedeće dozvole izračunajte oktalne reprezentacije, navedite radi li se o datoteci ili direktoriju i napišite što može svaki korisnik raditi:

- `-rwxr-x---`
- `drw-r--r--`
- `-rwxrwxrwx`
- `-r--r--r--`
- `-r-xr-xr--`

Napišite tekstualne reprezentacije sljedećih oktalnih dozvola:

- `755`
- `644`
- `700`

Za navedene zadatke morate ukratko prikazati izračune.

**Za ovaj zadatak predajete**:

- `rjesenje_4.txt` - izračuni i pojašnjenja za sve navedene dozvole

### 5. Zadatak (12 bodova)

Na Ubuntu Serveru instalirajte `git` alat ako već nije instaliran. Prebacite se u home direktorij vašeg korisnika. Naredbom `git clone <URL>` moguće je preuzeti udaljeni repozitorij na trenutni sustav - preuzmite repozitorij s vašeg GitHub korisničkog računa gdje vam se nalazi javni repozitorij za zadaće iz ovog kolegija.

Ako niste predavali zadaće, preuzmite javni repozitorij kolegija: `https://github.com/lukablaskovic/FIPU-OS`.

Dok se repozitorij klonira, otvorite novu terminal sesiju i provjerite u alatu za provjeru procesa detalje o ovom procesu:

- kojom naredbom je instanciran glavni proces?
- od koliko se potprocesa sastoji glavni proces?
- postoje li dretve? kako ćete to provjeriti?
- koji računalni resurs je najviše opterećen tijekom izvođenja procesa?
- koji je prioritet glavnog procesa?

**Ako ne stignete provjeriti (repozitorij se klonira prebrzo)**, možete naredbu pozvati ponovo, a klonirani direktorij s repozitorijem obrisati. Napišite naredbu koja će obrisati taj direktorij, na silu, skupa sa svim njegovim ugniježđenim sadržajem. Klonirajte repozitorij ponovo.

Kako ćete saznati `PID` glavnog procesa? Napišite barem 2 načina.
Kako ćete završiti proces kloniranja na silu? Napišite barem 3 načina.

Pozovite istu naredbu s višim prioritetom, a zatim spustite prioritet dok se proces izvodi. Napišite naredbe koje ste koristili.

Za ovaj zadatak predajete:

- `rjesenje_5.txt` - ručno upišite sve korištene naredbe i objašnjenja ako postoje
- `screenshot_8.png` - snimka zaslona koja prikazuje output tijekom kloniranja repozitorija
- `screenshot_9.png` - snimka zaslona koja prikazuje detalje o aktivnom procesu unutar odgovarajućeg alata
- `screenshot_10.png` - snimka zaslona koja prikazuje izmjene prioriteta procesa