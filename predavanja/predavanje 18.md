# Infrastruktura javnog ključa
 
- Skup elemenata:
    - Hardware, Software, Ljudi, Tehnika, Procedura
 
## Potpisani certifikati
- Izdaju ih poduzeča ( Certification Authority )
- Iden trust, Gold
 
- Elementi PKI-a:
    - CA ( Certificate Authority )
    - EU (End User)
    - Certificate
    - VA ( Validation Authority )
    - RA ( Registration Authority )
 
 
# Sigurnost e-maila
- SSL
- Digitalni Potpis
 
1. Računamo HASH
2. Pošiljatel kriptira HASH s priv. ključem
3. spajanje poruke s HASHom
4. Cjela poruka se kriptira
5. Kriptira se primateljevim javnim ključem
 
Primatelj:
1. Dekriptira svojim privatnim ključem
2. Ima slova
3. HASH provjeri pošiljateljevim javnim ključem
 
1. PGP ( Pretty Good Privacy)
 
# Crypt Analisys
- Sustav metoda kriptiranja i kriptiranih poruka s ciljem identifikacije potencijalne ranjivosti, kako bi dobili dekriptirani tekst
- Metoda kojom pokušavamo probiti kriptografske algoritme
- Težina ovisi o algoritmu
 
## Osnovne metode
- Brute force metoda - ( ovisi o hardware-u ), provodi se testiranjem svih mogučnosti jedna po jedna
- Frequency analysis - bazira se na proučavanju znakova / nizova znakova, i njihove pojavnosti u kriptiranom tekstu
- Prevara i obmana - social engineering za dohvačanje kriptografskih ključeva
- One-time pad - način šifriranja koje je matematički nemoguće razbiti, ali desi se da se više puta koristi isti ključ ( human error metoda )
 
## Metode koje koriste kriptoanalitičari
- Integralna - bazirana na diferencijalnoj ali koristi kombinatoriku i napredne mat. metode
- Diferencijalna - Kako ulaz utječe na izlaz kod simetričnih ključeva
- Linearna - ako imamo dovoljno parova čistog i kriptiranog teksta možemo otkriti ključ
 
## Napadi
- Brute Force - uspješnost ovisi o dužini ključa, vremenu, implimentaciji sustava (nakon 3 kriva unosa, blokira na 5 sati ... )
- Dictionary attack - ne testiraju nemoguće/moguće kombinacije nego riječi koje se inače koriste ( vrlo uspješno )
- Birthday attack - vrsta brute force napada, fokusira hash algoritme, bazira se na rođendanskom paradoxu ( vjerojatnost da 2 ili više ljudi u grupi imaju isti dan rođendan, veća je od 50% )
- Meet in the middle - koristi se za algoritme koji koriste više algoritama/ključeva za enkripciju ( netko kopa s jedne strane, neko s druge )
- Napad mjerenja vremena ( timing attack ) - random isprobavanje ključeva i vođenje tablice ( kako se algoritam ponaša kod raznih ulaza ) , s tim informacijama se probijaju drugi sustavi
- Rainbow table attack - koristi se za probijanje HASH-eva, tablica izračunatih vrijednosti hash-eva