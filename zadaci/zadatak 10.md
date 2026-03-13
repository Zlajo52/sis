# Phishing 

## Što je phishing?
Phishing je cyber napad u kojem napadač pokušava prevariti korisnika
kako bi dobio lozinke, podatke ili novac.

Cilja ljude, ne tehnologiju.
## Ciljevi phishinga
- Krađa vjerodajnica (lozinke, prijave)
- Širenje zlonamjernog softvera
- Krađa osjetljivih podataka
- Financijska prijevara (lažni računi, isplate)
   
## Phishing vs Spam

### Phishing
- Ciljan i uvjerljiv
- Oponaša stvarne osobe ili sustave
- Ima zlonamjernu namjeru

### Spam
- Masovno slanje poruka
- Uglavnom marketing
- Nema direktnu sigurnosnu prijetnju

## Tehnike phishinga

### 1. Lažno predstavljanje (Impersonation)
- Napadač se pretvara da je zaposlenik ili IT
- Često koristi besplatne domene (npr. gmail.com)
### 2. Socijalni inženjering
- Manipulacija emocijama:
  - hitnost
  - strah
  - znatiželja
- Primjeri:
  - “HITNO”
  - “Odmah pošalji podatke”
  - Zabrana kontakta prave osobe
### 3. Typosquatting
- Lažna domena s malom greškom
- Primjer:
  - glthub.com umjesto github.com
### 4. Punycode
- Zamjena slova sličnim znakovima
- Primjer:
  - ƒ umjesto f
- Otkriva se u email headerima (Return-Path)

### 5. Spoofing
- Email izgleda kao da dolazi s prave domene
- SPF, DKIM i DMARC ne prolaze provjeru
- Pravi pošiljatelj se vidi u Return-Path
### 6. Zlonamjerni privici
- HTML / HTA datoteke
- Mogu:
  - krasti lozinke
  - instalirati malware
- Često se maskiraju kao:
  - glasovne poruke
  - dokumenti

## Moderni phishing trendovi
- Manje malwarea u privicima
- Više krađe pristupa (credentials)
- Preusmjeravanje izvan sigurne mreže

## Legitiman alat kao mamac
- OneDrive
- Google Docs
- Dropbox

Cilj:
- Izgledati pouzdano
- Navesti korisnika na lažnu prijavu

## Lažne login stranice
- Kopije Microsoft / Google prijava
- Lažna domena
- Kradu korisničko ime i lozinku

## Side-channel komunikacija
- Prebacivanje komunikacije iz emaila:
  - SMS
  - WhatsApp / Telegram
  - Poziv
- Izvan kontrole tvrtke

# Socijalni inženjering (Social Engineering)

## Što je socijalni inženjering?
Socijalni inženjering je tehnika u kojoj se manipulira osobom kako bi napravila grešku, npr.:
- otkrila lozinku
- otvorila zlonamjernu datoteku
- odobrila lažno plaćanje

Napad cilja ljude, a ne računala,
zbog čega se često naziva i „hakiranje ljudi“.

## Psihološki faktori   
Napadači koriste:
- hitnost
- znatiželju
- autoritet
- strah

Cilj je natjerati korisnika da reagira bez razmišljanja.

## Vrste phishinga
- Email phishing
- Smishing (SMS poruke)
- Vishing (telefonski pozivi)
- Quishing (QR kodovi)
- Poruke na društvenim mrežama

## Zašto je phishing opasan?
- Sve je teže prepoznati lažne poruke
- Čak i oprezni korisnici mogu nasjesti
- Poruke izgledaju stvarno i uvjerljivo

# S.T.O.P. – zaštita od phishinga

## Provjera poruke (S.T.O.P.)
- S – Je li poruka sumnjiva?
- T – Traži li da kliknem nešto?
- O – Nudi li predobru ponudu?
- P – Pritisće li me da reagiram odmah?

## Kako reagirati (S.T.O.P.)
- Uspori – napadači koriste paniku
- Upiši adresu ručno
- Ne otvaraj neočekivane privitke
- Provjeri pošiljatelja (pravu adresu)


# Izrada phishing zamke (teorija)

## Što je phishing zamka?
To je lažan sadržaj koji izgleda legitimno
i služi za prijevaru korisnika.

Primjeri:
- lažna login stranica
- lažni dokument
- lažna obavijest

## Cilj phishing zamke
- Krađa korisničkog imena i lozinke
- Dobivanje pristupa sustavu
- Financijska prijevara

## Ključ uspjeha napada
- Uvjerljiv sadržaj
- Poznat pošiljatelj
- Realan razlog poruke
- Prava poruka u krivo vrijeme

# Dostava phishing poruke (teorija)

## Kako phishing izgleda uvjerljivo?
- Poruka izgleda kao da dolazi od poznate tvrtke
- Tema je relevantna za žrtvu
- Nema očitih grešaka

## Što phishing email obično sadrži?
- Lažni pošiljatelj
- Uvjerljiv predmet poruke
- Link ili zahtjev za radnju
- Osjećaj hitnosti                 

## Zaključak
Phishing ne napada sustave,
nego povjerenje ljudi.

Najbolja obrana je:
- pažnja
- provjera
- usporavanje reakcije