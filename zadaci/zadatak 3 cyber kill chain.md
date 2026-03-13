### Cyber kill chain
- okvir je za kibernetičku sigurnost
- stvoren je kako bi pomogao organizacijama u obrani od kibernetičkih napada razumijevanjem načina na koji se provode

podijeljen je na 7 segmenata:
1. **izviđanje**
- prikupljanje informacija o ranjivostima i slabostima mete kako bi otkrio potencijalne ulazne točke
- pasivno(neprimjetno, koristeći inteligenciju otvorenog koda)
- aktivno( traži od hakera neku vrstu kontakta s metom)
- obrana - smanjena količina javno dostupnih info., praćenje i analiza mrežnog prometa, koristiti uslugu zaštite sigurnosti
2. **naoružavanje**
- kreiranje štetnog sadržaja
- mnogi napadači koriste npr. kriptiranje kako bi izbjegli otkrivanje(mogu ga sakriti u datoteci, poput MS Word ili PDF datoteke)
- **Exploit kit** 
je automatizirana platforma koja sadrži različite exploite za razne ranjivosti. Te platforme olakšavaju napadačima pakiranje exploit koda unutar payloada, poput izvršne datoteke ili određenih dokumenata
- obrana - edukacija korisnika, onemogućiti nepotrebne značajke, deinstalirati nepotrebni softver i ukloniti nepotrebne dodatke preglednika
3. **isporuka**
- načini: Phishing e-mailovi, Spear phishing e-mailovi, Zlonamjerne web poveznice, Platforme za dijeljenje datoteka, Malvertising, SMS phishing (Smishing), Socijalni inženjering, Fizička sredstva isporuke
- obrana - edukacija korisnika, filtriranje e-pošte i weba, Web application firewalli (WAF) neizostavni su za blokiranje zlonamjernih datoteka, nadzor mreže i upravljanje zakrpama
4. **iskorištavanje**
- npr. ciljano napadanje sustava koji se oslanja na lozinke, softverske ranjivosti, SQL injection, buffer overflow
- obrana - multi-factor authentication (MFA), upravljanje zakrpama (patch management) za servere i klijente, sustavi za prevenciju upada
5. **instalacija**
- osigurava trajni pristup iskorištenom sustavu
- napadači se mogu poslužiti instaliranjem malwarea, kreiranjem backdoora ili instaliranjem rootkita
- obrana - pratiti nove procese i servise, Endpoint Detection and Response (EDR) omogućava nadzor endpointa za sumnjive aktivnosti, redovite sistemske revizije i usporedbe sa sigurnom osnovnom konfiguracijom
6. **C2, upravljanje i kontrola**
- cilj uspostaviti taj prikriveni komunikacijski kanal za upotrebu u sljedećoj fazi, napadač postavlja C2 komunikacijski kanal između kompromitiranih sustava i vlastite infrastrukture( npr. registracije domena, IP adresa i korištenja cloud servisa, društvenih mreža, i sl)
- obrana - nadzor mreže putem firewalla, IDS-a i IPS-a, nadzor DNS prometa i analiza, nadzor web prometa, inspekcija enkripcije
7. **poduzimanje akcije nad ciljevima**
- ostvarivanje namjere, koja se kreće od krađe podataka (data exfiltration) do ometanja rada sustava
- pr. napada - ransomware napad, očiti, krađa podataka (data exfiltration), manipulacija industrijskim kontrolnim sustavima (ICS)
- obrana - Data Loss Prevention (DLP), pouzdan plan sigurnosnog kopiranja i oporavka, segmentaciju mreže i stroge kontrole pristupa, Praćenje korisničkih aktivnosti, Endpoint Detection and Response (EDR)