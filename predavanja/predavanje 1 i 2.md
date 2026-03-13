## SIGURNOST INFORMACIJA(PODATAKA)
- **PODATAK** - činjenica koja se može zapamtiti
- **INFORMACIJA** - podatak na bazi kojeg stvaramo odluku
- više info. = bolja odluka

### Najvažnije stvari kod sigurnosti informacija:
1. povjerljivost
2. integritet
3. dostupnost

### CIA trokut
- da bi info bile sigurne moraju biti zadovoljeni svi uvijeti za sigurnost
- **kršenja**
1. nepažnja
2. zlonamjerni korisnici
3. kvarovi
4. uskraćivanje pristupa

### Povjerljivost
- podrazumijeva tajnost info.
- dostupno samo onima koji za to imaju dozvolu
- ***autorizacija*** - potreba tajnih podataka  

### Integrititet
- promjena podataka nije potrebna ako se to nužno ne mora mijenjati
- mjenjanje integrititeta: 
    - kvarovi
    - nepažnja
    - zlonamjerni korisnici

### Dostupnost
- prekidanje servisa
- bitno je za donošenje odluka

<br>
- Autentifikacija - potvrda da smo mi oni koji jesmo(stvarna info)
<br>
- Neporecivost - osigurava da ne možemo poreći ono sto smo napravili(osigurava se digitalnim potpisima) 

## NAPAD
- dokaz cyber napada:
-ranjivost, metoda napada, motiv/cilj

**VRSTE NAPADA**
- **aktivni napadi** - napadi  u kojima mi imamo direktan utjecaj na sustav koji napadamo i s njime dolazimo u konkretan odnos/susret ( dos,mitm, otimanje sesije, sql incection, zlonamjerni softver(malware))
- **pasivni napadi** - svode se na nadgledanje mete(sniffing, prisluškivanje)
- **close in napadi** - u direktnoj blizini mete (socijalni inžinjeri npr. prisluškivanje osobe, shoulder surfing, dumpster diving)
- **insiderski napadi** - napadi zaposlenika na vlastitu firmu iznutra
- **distribucijski napadi** - mogu biti hardverski i softverski, napadi na lanac opskrbe

## Model za prepoznavanje kibernetičkih napada
- **cyber kill chain** - (lockheed martin), omisljen za sto prije detektiranje napada, model kako se napadac ponasa
1. izviđanje
2. naoružavanje
3. isporuka
4. iskorištavanje
5. instalacija
6. C2, upravljanje i kontrola
7. poduzimanje akcije nad ciljevima
- svi napadači prolaze ove korake kako bi napali neki sustav
