# Incident Response Process

Incident Response (IR) je proces kojim organizacija otkriva, analizira i reagira na cyber napade. Cilj je smanjiti štetu, ukloniti prijetnju i spriječiti ponavljanje.

Koriste se planovi, procedure i alati (SIEM, EDR, IDS).

### Najviše se koriste 2 okvira:

1. NIST Incident Response Framework

2. SANS Incident Response 101

### NIST Incident Response – 4 faze

1. Preparation (Priprema)
Postavljanje planova, alata, procedura i tima.

2. Detection & Analysis (Otkrivanje i analiza)
Prepoznavanje incidenta, provjera logova, analiza anomalija, potvrda da se radi o napadu.

3. Containment, Eradication & Recovery

- Containment: Zaustavljanje širenja napada

- Eradication: Uklanjanje prijetnje

- Recovery: Vraćanje sustava u normalno stanje

4. Post-Incident Activity
Pregled incidenta, lekcije naučene, ažuriranje planova.

NIST se promatra kao ciklus, ne lista zadataka – svaka faza unaprijedi sljedeću.

### SANS Incident Response – 6 koraka

1. Preparation
2. Identification
3. Containment
4. Eradication
5. Recovery
6. Lessons Learned

### “Security is a process” – Bruce Schneier

Sigurnost nije proizvod – to je nastavak rada, poboljšavanja, praćenja i reagiranja. IR je stalni ciklus, ne jednokratni zadatak.

## 1. Containment (Obuzdavanje)

- Cilj obuzdavanja je spriječiti širenje incidenta kroz sustav ili mrežu.
- U ovoj fazi se incident izolira, napadaču se smanjuje manevarski prostor i sprečava daljnja šteta.

### Glavne ideje:

- izolirati kompromitirane segmente,
- zaustaviti aktivne zlonamjerne procese,
- prikupiti relevantne IoC-ove (IP, domena, URL, hash, artefakti),
- provjeriti IoC-ove u SIEM/EDR sustavima.

## 2. Eradication & Recovery

- Nakon što je incident obuzdan, cilj je ukloniti sve tragove napada i vratiti sustav u sigurno stanje.

### Glavne ideje:

- ukloniti zlonamjerne datoteke, konfiguracije, artefakte i persistence mehanizme,
- osigurati čiste verzije sustava i datoteka,
- provjeriti da nema dodatnih kompromitacija prije povratka u produkciju.

## 3. Post-Incident Activity

- Ova faza služi za učenje i poboljšanje.

### Glavne ideje:

- pregled i analiza cijelog incidenta,
- izrada “lessons learned” dokumenta,
- ažuriranje sigurnosnih politika i planova,
- poboljšanja u alatima, procesima i edukaciji zaposlenika.

Primjeri poboljšanja:

- jači EDR sustavi,
- bolja kontrola web prometa,
- edukacija o makro datotekama,
- blokiranje visokorizičnih funkcija (npr. makroa).
# Zaključak

### Incident Response je kontinuiran ciklus:

Priprema → Detekcija → Analiza → Obuzdavanje → Uklanjanje → Oporavak → Lekcije naučene → Nova priprema

### Svrha:
Zaštititi organizaciju, smanjiti štetu i spriječiti ponovni napad.