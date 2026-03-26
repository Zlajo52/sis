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
- 