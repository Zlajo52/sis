# Cyber Threat Intelligence (CTI) za SOC L1 analitičare

## SOC
 - je bučno okruženje puno alertova i telemetrije; L1 analitičar je prvi koji reagira na svaki sumnjivi IP, pop-up ili paket.

## CTI
- daje kontekst i pomaže odlučiti koji alert je stvarna prijetnja.

Cilj: prijeći s „prepoznajem IP“ → „znam zašto je IP opasan i mogu dokazati“.

Brza procjena L1 analitičara daje IR timu više vremena za reakciju.

### Tri ključna pitanja CTI-ja

1. Tko ili što je na drugoj strani indikatora?
2. Kako se ponašao u prošlosti?
3. Što moja organizacija treba učiniti sada?

Podaci – informacije – inteligencija

- Podaci: neobrađeni artefakti (npr. IP: 45.155.205.3)
- Informacija: podaci + faktualni kontekst (npr. registriran kod Hetznera)
- Inteligencija: analizirani podaci s odgovorom „so-what“ (npr. pripada BumbleBee C2 → blokirati)

## Vrste indikatora

IOC (Indicator of Compromise): dokaz kompromitacije (C2 adresa)

IOA (Indicator of Attack): zlonamjerna aktivnost u tijeku (PowerShell pokreće nepoznati servis)

TTP (Tactics, Techniques, Procedures): metode napadača (MITRE ATT&CK tehnike)

### Najvažniji indikatori i alati za provjeru

- IP: WHOIS, VirusTotal, Shodan
- Domene: Passive DNS, SecurityTrails
- URL: URLhaus, urlscan
- Hash: VirusTotal, Hybrid-Analysis
- Email: MXToolbox, Have I Been Pwned
- Lokalni artefakti: EDR, Sigma pravila

### Feed vs. Platforma

- Feed: automatski tok indikatora (CSV, JSON, STIX)
- Platforma: MISP, OpenCTI – pohrana, mapiranje, TLP oznake
- Previše feedova = puno lažnih pozitivnih

## Izvori CTI-ja

- Interna telemetrija (SIEM, EDR, phishing) – najrelevantnija
- Komercijalni servisi – visoka kvaliteta, ali s ograničenjima
- OSINT – javni blogovi, AbuseIPDB (provjeriti dvaput)
- Zajednice / ISAC – sektorski kontekst

### Tipovi CTI-ja

- Strateški: trendovi i rizici za poslovne odluke
- Taktički: analiza TTP-a
- Operativni: detalji kampanja i ciljani resursi
- Tehnički: IP, hash, domene (L1 često eskalira)

 ### Traffic Light Protocol (TLP)

- CLEAR: slobodno dijeljenje
- GREEN: zajednica / partneri SOC
- AMBER: unutar organizacije / need-to-know
- RED: samo imenovani primatelji

## CTI životni ciklus (6 faza)

1. Direction (smjer): definirati što tražimo i zašto
2. Collection (prikupljanje): skupljanje sirovih podataka
3. Processing (obrada): normalizacija, deduplikacija, označavanje, priprema akcijskih datoteka
4. Analysis (analiza): procjena relevantnosti i rizika
5. Dissemination (distribucija): slanje pravim timovima u odgovarajućem formatu
6. Feedback (povratne informacije): mjerenje učinkovitosti i poboljšanje procesa

### Standardi i okviri

- MITRE ATT&CK: katalog napadačkih tehnika
- MITRE D3FEND: obrambene tehnike

Cyber Kill Chain: 7 faza napada (Recon → Weaponization → Delivery → Exploitation → Installation → C2 → Actions)

CVE / CVSS / NVD: ranjivosti, ocjene i službena baza

### STIX & TAXII

- STIX: format za opis indikatora (JSON)
- TAXII: protokol za sigurnu razmjenu CTI-ja u realnom vremenu

### Dodatne napomene

Dijeljenje CTI-ja jača kolektivnu obranu, ali treba paziti na privatnost i TLP oznake.

Izvještaji poznatih kompanija (Mandiant, Recorded Future, Unit42) pomažu konsolidirati CTI za stakeholder-e.

# Threat Intelligence – CTI

- Analiza podataka i informacija pomoću alata i tehnika za prepoznavanje obrazaca prijetnji i načina zaštite.
- Cilj: smanjiti rizik od postojećih ili novih prijetnji prema organizacijama, sektorima ili državama.

## Ključna pitanja za mitigaciju rizika

1. Tko vas napada?
2. Koja je njihova motivacija?
3. Koje su njihove sposobnosti?
4. Koje artefakte i indikatore kompromitacije trebamo pratiti?

## Klasifikacija Threat Intelligence

- Strategic Intel: Pregled prijetnji na visokoj razini, trendovi i rizici za poslovne odluke.
- Technical Intel: Dokazi i artefakti napada; koristi IR tim za kreiranje baseline površine napada i obranu.
- Tactical Intel: Analiza TTP-a (tactics, techniques, procedures) napadača; jača sigurnosne kontrole.
- Operational Intel: Motivi i ciljevi napadača; pomaže razumjeti kritične resurse u organizaciji.

## Alati za analizu URL-a i weba

- Urlscan.io:

Automatski pregled web stranica, zapis domena, IP-a, resursa, tehnologija, cookies, ponašanja.

-Pregled rezultata: Summary, HTTP, Redirects, Links, Behaviour, Indicators.

- Abuse.ch platforme

-MalwareBazaar: baza i analiza malware uz upload, YARA pravila, ClamAV i tagove.

FeodoTracker: praćenje botnet C2 servera (Emotet, Dridex, TrickBot).

SSL Blacklist: blok lista zlonamjernih SSL certifikata i JA3/JA3s fingerprintova.

URLhaus: dijeljenje zlonamjernih URL-ova za distribuciju malware-a.

ThreatFox: dijeljenje i preuzimanje IOCs (MISP, Suricata IDS, JSON, CSV).

## Email phishing i alati

PhishTool: analiza phishing emailova, OSINT heuristika, klasifikacija, izvještaji.
- Community verzija: analiza metapodataka, praćenje URL-a i privitaka.
- Enterprise verzija: integracija s M365/G Workspace, praćenje prijava phishinga.

Ključne funkcije: Headers, Received Lines, X-Headers, Security, Attachments, Message URLs, Resolve.

## Cisco Talos

Tim za prikupljanje i analizu CTI-ja, pruža actionable intel i zaštitu.

6 ključnih timova:

1. Threat Intelligence & Interdiction
2. Detection Research
3. Engineering & Development
4. Vulnerability Research & Discovery
5. Communities
6. Global Outreach

Alati: Vulnerability Information (CVE, CVSS), Reputation Center (IP, SHA256, email/spam).