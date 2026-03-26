# protumjere i sigurnost kljuceva 
## 
- u organizacijama trebamo konf ids da prati promjene 
- ključevi ne smiju biti prisutni u izvornom kodu
- kada biramo simetricne algoritme, vodimo brigu da su kljucevi sto veci po pitanju bitova (min 256)
- za asimetricne algoritme vrijedi isto samo moraju biti duzi (min 2048)
- koristiti gotove isprobane alate i ne koristiti vlastite
- kad koristimo hash algoritme, koristimo one koji su dokazano trenutno neprobojni
- često rotirati ključeve (promijeniti lozinke svakih 6 mjeseci)
- preferira se fraza umjesto lozinke
- privatne kljuceve nigdje nebi trebali dijeliti
- pratiti trendove i azurirati sigurnosne sustave prema njima

## tehnike kad radimo s kljucevima
- salting - na izvorni podatak dodajemo neki znak kako se nebi mogla otkriti kolizija
- key stretching- produljenje i pojacanje kljuca koji je potencijalno slab cime se smanjuje mogucnost brute force napada

# MALWARE
## vrste:
- trojan
- backdoor
- rootkit
- ransomware
- virusi
- crvi
- spyware
- crypter
- botnet
---
## vrste podsustava za malware(komponente)
- crypter (štiti malware od analize i reverznog inzinjeringa)
- downloader (podsustav koji automatski skida drugi malware)
- dropper (podsustav koji instalira i izvrsava drugi malware)
- exploit (programski kod koji koristi ranjivost sutstava kako bi pristupio informacijama ili inst malware)
- injector (umeće kod u druge aktivne ranjive procese)
- ofuscator (podsustav koji skriva izvorni kod i njegovu svrhu)
- packer (pakira sve dijelove malwarea u jednu cjelinu koja je najčešće arhivirana i može se jednostavno izvršiti)
- payload (kod koji izvodi ranjivost nakon što je ušao u sustav)
- malicious code (kod koji definira osnovnu funkcionalnost malwarea)
