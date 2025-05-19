## Zadaci za vježbu: OS4 - Rad na Virtualnom stroju

### Zadatak 2: Git - the information manager from hell 🔥

Git je najpopularniji alat za verzioniranje programskog koda. Prvu verziju je razvio Linus Torvalds, 2005. godine, radi potrebe za boljim alatom verzioniranja koda za Linux, budući da je razvoj Linuxa uključivao veliku zajednicu programera diljem svijeta.

1. Instalirajte `git` na vašem Ubuntu serveru i provjerite verziju. GitHub platforma nastala je nekoliko godina kasnije s ciljem pružanja jednostavnijeg načina upravljanja projektima i suradnje, gdje se kolaboracija temelji na `git`-u. Samim time, i `git` kao paket je dostupan na GitHub platformi - `https://github.com/git/git.git`, skupa sa cijelom svojom povijesti verzioniranja.

2. Naredbom `git clone <web_poveznica>` preuzmite cijeli repozitorij s GitHub-a na VM, a prije toga se se prebacite u _home_ direktorij.

3. Provjerite je li repozitorij uspješno preuzet te se prebacite u preuzeti direktorij. Svako dodavanje sadržaja (ažuriranje datoteka) u repozitorij se naziva _commit_, a verzioniranje nam omogućuje da se vratimo na prethodnu verziju projekta u bilo kojem trenutku. Uz svaki _commit_, dodaje se i poruka koja opisuje što je promijenjeno. U CLI-u, otvorite _manual_ `git` paketa i proscrollajte do odjeljka `HIGH-LEVEL-COMMANDS` - pronađite naredbu koja će ispisivati _logove_ (povijest) svih _commit_-ova.

_Hint:_ Unutar _manuala_ možete pretraživati ključne riječi tako što pritisnete `/`, upišete ključnu riječ i pritisnete `Enter`. Da biste se kretali kroz rezultate pretraživanja, koristite `n` za sljedeći rezultat i `N` za prethodni rezultat.

4. Jendnom kad ste pronašli odgovarajuću naredbu, pokušajte ispisati sve _commit_-ove unutar repozitorija. Vidjet ćete da su poredani po vremenu, od najnovijeg prema najstarijem. Vaš zadatak je pronaći prvi _commit_ i njegovu poruku koju je Linus Torvalds napisao davne 2005. godine. Otvorite _manual_ `git` paketa i pronađite zastavicu koja će vam omogućiti da ispišete _logove_ obrnutim redoslijedom. Na crtu napišite poruku prvog _commit_-a i njegov datum:

<hr>

5. Povezivanjem na VM putem SSH možemo učiniti i nešto zanimljivijim, npr. zašto ne bismo korisniku napisali neku poruku dobrodošlice svaki put kad se poveže, da nije smo onaj dosadni _Welcome to Ubuntu_ zaslon.

6. Unutar _home_ direktorija napravite novi direktorij proizvoljnog naziva i prebacite se u njega. Unutar njega napravite novi `node` projekt koristeći napredbu `npm init -y`. Ova naredba će napraviti `package.json` datoteku koja sadrži osnovne informacije o `node` projektu. Otvorite ju pomoću CLI uređivača i pod "author" ključem unesite svoje ime i prezime (i ime i prezime drugog člana tima, ako radite u paru). Spremite datoteku i zatvorite uređivač.
7. Koristeći `npm` naredbu, instalirajte paket `greetings`. Sintaksa je: `npm install <ime_paketa>`. Stvorite novu JavaScript datoteku, npr. `welcome.js` i u nju upišite sljedeći kod:

```javascript
const greet = require("greetings");
console.log(greet());
```

- svaki put kada pokrenete ovu datoteku, ispisat će se pozdrav na drugom jeziku.

7. Unutar istog direktorija dodajte novu `bash` skriptu. Bash skripta treba ispisati poruku dobrodošlice za trenutnog korisnika kombiniranjem Unix varijable `$USER` i pozivanjem `welcome.js` JavaScript datoteke. Na primjer, ako je trenutni korisnik `markomaric`, skripta može ispisati: `Yo markomaric`.

Preporuka: u bash skriptu upišite apsolutnu putanju do `welcome.js` datoteke.

8. Potrebno je još samo pozvati bash skriptu prilikom prijave na VM. To možete napraviti na 2 načina:

- dodavanjem poziva skripte u `~/.bashrc` datoteku
- dodavanjem poziva skripte u `~/.ssh/rc` datoteku

Nakon dodavanja, možete restartirati VM i shell sesiju ili _reloadati_ datoteke koristeći `source ~/.bashrc` ili `source ~/.ssh/rc`.

9. Povežite se na VM putem SSH-a i provjerite ispisuje li se poruka dobrodošlice s vašim imenom (za povezivanje odaberite mrežni adapter po izboru).
