## Zadaci za vježbu: OS4 - Rad na Virtualnom stroju

### Zadatak 1: Ubuntu Server, JavaScript, Node.js i krave 🐮

Članovi tima: <span>********************************************************************************************************************************\_********************************************************************************************************************************</span>

Naučili ste da se JavaScript može pokretati u web pregledniku - jednostavno otvorimo web konzolu i možemo pisati i izvršavati JavaScript kod. Međutim, moguće ga je pokretati i izvan okruženja web preglednika, koristeći `Node.js` okruženje - pa i na Linuxu.

1. Pokrenite Ubuntu Server preko VirtualBox-a. Upute za instalaciju možete pronaći u skripti _OS4 - Rad na Virtualnom stroju: Uvod_. Ako ste već instalirali Ubuntu Server, preskočite ovaj korak.
2. Ažurirajte lokalnu listu paketa i verzija te instalirajte pakete `nodejs` i `npm` (_Node Package Manager_). Npm je alat koji se koristi za instalaciju i upravljanje paketima u Node.js okruženju.
3. Provjerite jesu li navedeni paketi uspješno instalirani i napišite na crtu kako to možete provjeriti na barem 2 načina.

<span>**************************************************************************************************************************************\_**************************************************************************************************************************************</span>

4. Pokrenite naredbu `node` u terminalu - to će otvoriti Node.js REPL okruženje u koje možete direktno pisati JavaScript kod, cool zar ne? Osim toga, ako se uz istu naredbu navede i putanja do datoteke, Node.js će izvršiti JavaScript kod definiran u toj datoteci. Prebacite se u _home_ direktorij i napravite `node_project` direktorij.
5. Napravite datoteku `hello.js` unutar novog direktorija te u nju pohranite vaše ime i prezime u varijablu (pohranite i drugog člana u dodatnu varijablu, ako radite u paru) i ispišite poruku u konzolu: `Pozdrav ja sam/mi smo <ime i prezime> i uspješno sam pokrenuo JS u Node.js okruženju!` koristeći interpolaciju stringova.
6. Instalirajte Debian paket `cowsay` koji će ispisivati poruke u obliku krave 🐮. Unutar istog direktorija, napišite bash skriptu koja očekuje jedan argument, ako korisnik nije proslijedio točno 1 argument vratite grešku i prekinite izvođenje skripte.
7. Ako je korisnik proslijedio točno 1 argument, vrijednost argumenta pohranite u varijablu `poruka` i pozovite `cowsay` naredbu s tom porukom unutar bash skripte.
8. Pozovite bash skriptu, a kao argument proslijedite rezultat izvođenja `node hello.js` datoteke. Napišite kako ste to napravili:

<span>**************************************************************************************************************************************\_**************************************************************************************************************************************</span>

9. Kako ćete proučiti paket `cowsay` u CLI-u? Konkretno, zanimaju vas dostupne zastavice koje možete koristiti prilikom pozivanja `cowsay` naredbe. Primjerice: pohlepna krava, umorna krava, paranoična krava, itd. Na crtu napišite sve dostupne zastavice koje ste pronašli i napišite kako ste ih pronašli.

<span>**************************************************************************************************************************************\_**************************************************************************************************************************************</span>

10. Jednom kad ste pronašli odgovarajuće opcije, nadogradite vašu bash skriptu tako da korisnik može proslijediti i jednu od odgovarajućih zastavica, a ako proslijedi neispravnu zastavicu, ispišite grešku i prekinite izvođenje bash skripte. Ako proslijedi ispravnu zastavicu, proslijedite ju `cowsay` naredbi. _Hint:_ bash lista.
