## Linux logging for SOC
- sustavi temeljeni na Linuxu nisu imuni na malware
- Linux zapisuje većinu događaja u obične tekstualne datoteke. To znači da možete čitati logove putem bilo kojeg tekstualnog uređivača, bez potrebe za specijaliziranim alatima poput Event Viewera
- većina Linux logova nalazi se u mapi /var/log
### Filtriranje logova

Linux logovi mogu sadržavati tisuće događaja, ali za SOC su korisni samo neki. Zato se logovi filtriraju, npr. pomoću grep naredbe:

grep CRON → prikazuje samo CRON događaje

grep -v CRON → isključuje CRON događaje

### Otkrivanje logova

Ako tražite, npr., korisničke prijave, možete pretražiti sve logove u /var/log/ pomoću ključnih riječi poput login, auth ili session.

### Posebnosti logiranja

Linux dopušta promjenu formata logova, njihove razine detalja i lokacije pohrane, pa se logovi mogu razlikovati između distribucija

### Autentikacijski logovi
- Najvažnija log datoteka za praćenje je /var/log/auth.log
- Korisnici se mogu prijaviti: lokalno, preko SSH-a, koristeći sudo ili su, ili automatski za cron zadatke.

Svaka uspješna prijava i odjava se zapisuje

- SSH daemon bilježi uspješne i neuspješne prijave
- Za praćenje promjena korisnika koristi se useradd, usermod, userdel i passwd.

Sudo komande mogu otkriti maliciozne aktivnosti

### Opći sistemski logovi
- /var/log/kern.log — kernel poruke i greške, korisno za naprednu istragu;

- /var/log/syslog (ili /var/log/messages) — objedinjeni stream raznih događaja;

- /var/log/dpkg.log (ili /var/log/apt) — zapisnik upravitelja paketa na Debian-based sustavima;

- /var/log/dnf.log (ili /var/log/yum.log) — zapisnik upravitelja paketa na RHEL-based sustavima.

### Bash history 
zapisuje naredbe iz interaktivne sesije (po izlasku se sprema u ~/.bash_history), ali ne bilježi neinteraktivne komande (cron, servisi), napadači mogu izbjegavati zapis dodavanjem vodećeg razmaka, pokretanjem skripti ili korištenjem drugih shellova koji ne logiraju.

### Praćenje u stvarnom vremenu (Runtime Monitoring)
Tri razine praćenja:

1. Monitor samo auth.log – usko logiranje, otkriva jedan tip prijetnje.
2. Dodaj web logove i Bash history – šire logiranje, otkriva više prijetnji.
3. Ignoriraj runtime događaje – nepotpuno logiranje, propušta prijetnje.

 - Sistemski pozivi (system calls) su osnova praćenja — sve moderne EDR i audit alati ih koriste.

- Alati poput auditd omogućuju praćenje i zapisivanje odabranih sistemskih poziva.

- Šire logiranje (web logovi, Bash history) pomaže u otkrivanju više prijetnji, ali nije dovoljno bez runtime praćenja.

### Audit Daemon (auditd)

Auditd je ugrađeno rješenje za praćenje runtime događaja, često korišteno u SOC timu. Fokus je na čitanju pravila i tumačenju rezultata.

- Auditd zapis dijeli događaj u više linija:

1. PROCTITLE – komandna linija procesa
2. CWD – trenutni radni direktorij
3. SYSCALL – detalji sistemskog poziva
- Alternativni alati (Sysmon, Falco, Osquery, EDR) također koriste sistemske pozive za runtime monitoring

ZAKLJUČAK
-
- Linux logovi mogu biti kaotični, ali često sadrže dovoljno informacija za otkrivanje prijetnji.
- Logovi se po defaultu čuvaju u /var/log/ i uglavnom su u običnom tekstu.

### Tri najvažnija log izvora za SOC:

1. auth.log – autentikacija i upravljanje korisnicima
2. Logovi specifičnih aplikacija – web serveri, baze podataka, mail serveri
3. Runtime logovi – procesi, datoteke, mreža (auditd ili alternative)

- Bash history je nepouzdan za SOC; bolje koristiti auditd ili alternativna rješenja za praćenje runtime događaja.

## WEB napadi
- Web napadi su jedan od najčešćih načina na koji napadači ulaze u ciljane sustave
- Client-side napadi

### Client-side napadi 
- iskorištavaju slabosti u ponašanju korisnika ili na njegovom uređaju. Često ciljaju ranjivosti u preglednicima ili varaju korisnika da izvrši nesigurne radnje kako bi napadač pristupio računima ili ukrao osjetljive podatke
- mogu krasti podatke ili manipulirati okolinom bez sumnjivih HTTP zahtjeva

### Ograničenja SOC-a
- Otkrivanje ovih napada s SOC perspektive je često teško ili nemoguće bez dodatnih kontrola na korisničkoj strani ili endpoint monitoring-a.

### Uobičajeni client-side napadi
1. Cross-Site Scripting (XSS) – maliciozni skript se izvršava u pregledniku korisnika unutar legitimne web stranice
2. Cross-Site Request Forgery (CSRF) – preglednik šalje neautorizirane zahtjeve u ime korisnika
3. Clickjacking – napadači prekrivaju legitiman sadržaj nevidljivim elementima kako bi prevarili korisnika da klikne nešto nesigurno

### Server-side napadi
- Server‑side ranjivosti direktno ugrožavaju podatke i servise na serveru.
- Pravilno logiranje i analiza mrežnog prometa su ključni za otkrivanje ovih napada.
- Obrana uključuje valjanu validaciju/filtriranje ulaza, korištenje parametriziranih upita i pravilne konfiguracije servera.
- Automatizirani napadi (poput brute‑force) se mogu smanjiti ograničavanjem pokušaja i korištenjem MFA.
- Incident response na server‑side napade često zahtijeva pregled aplikacijskih logova, web server logova i capturea mrežnog prometa

### Uobičajeni server‑side napadi (jedna rečenica po stavci)
1. Brute‑force: automatsko ponavljanje korisničkih imena i lozinki dok se ne pogodi ispravna kombinacija.
2. SQL Injection (SQLi): napadač mijenja SQL upit kroz nesiguran unos kako bi pristupio ili izmijenio podatke u bazi.
3. Command Injection: aplikacija prosljeđuje korisnički unos u sistemske komande bez provjere, pa napadač izvršava naredbe na serveru.

### Logovi
- Logovi mogu biti vrijedan alat za otkrivanje web napada

### Network traffic analysis
- omogućuje analizu stvarnih podataka koje šalju klijent i server.
- Snimanje i pregled paketa otkriva detaljno ponašanje napadača, uključujući transport protokole i aplikacijske podatke.
- Network capture pokazuje više nego server logovi: HTTP header-e, POST body, kolačiće, uploadane i downloadane datoteke.
- Enkriptirani protokoli (HTTPS, SSH) ograničavaju vidljivost podataka bez ključeva za dešifriranje.
- Fokus za primjere je na HTTP prometu, jer je čitljiv i koristan za analizu napada.

### WAF (Web Application Firewall) 
- štiti web aplikacije, pregledava kompletne HTTP zahtjeve i može dešifrirati TLS promet prije nego što stigne do servera.

- Funkcija: odlučuje hoće li zahtjev proći ili biti blokiran prema pravilima.

### Vrste pravila:
1. Blokiranje poznatih napada: npr. User-Agent sqlmap.
2. Zabranjivanje zlonamjernih izvora: IP reputacija, geo-blokiranje.
3. Prilagođena pravila: specifična za aplikaciju, npr. dozvoliti GET/POST samo na /login.
4. Rate-limiting / prevencija zloupotrebe: ograničenje broja zahtjeva po minuti po IP-u.

- Challenge-response mehanizmi: CAPTCHA za provjeru stvarnih korisnika i blokadu botova (bot traffic ~37% globalnog web prometa).
- Integracija threat intelligence: WAF može automatski blokirati poznate zlonamjerne IP-eve i User-Agente, koristi ažurirane liste za zaštitu od novih prijetnji, uključujući APT grupe i CVE-ove.
- Prednost WAF-a: štiti aplikaciju proaktivno, filtrira zlonamjerne zahtjeve prije nego dođu do servera, smanjuje rizik od SQLi, XSS i drugih web napada.