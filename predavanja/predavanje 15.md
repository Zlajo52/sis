# Banner grabing / Capture the flag
 
- skeniranje OS-a kako bi saznali što je na portu kako bismo izrdili točan malware
 
### Tipovi otkirvanja
1. aktivno -> dolazimo u direktnu interakciju i dobivamo odgovore pomoću kojih zaključujemo o verziji i tipu OS-a
2. pasivno -> sjedimo negdje u mreži i snifamo promet (error messages, protokoli)
 
### Alati za banner grabing
1. Wireshark
2. Nmap -> (-O. -sV)
3. Unicornscan
4. Nmap scripts
 
### Protumjere za banner grabing
- lažiranje sustava (banera)
- uklanjanje ekstenzija (teže otkriti što se gdje koristi i radi)
- zaobiči običajene protumjere
 
### Zaobilaženje protumjera
- spufanje IP adresa -> staviti lažnu IP adresu
- Firewallovi su blago receno glupi
- maniplacija izvornim portom
- fragmentacija paketa -> funkcija TCP protokola, (-F -> za uključivanje fragmentacije)
- skeniranje upotrebom mamaca -> zavaravamo protivnika tako da paketi dolaze s više hostova (-D, -RND)
- IP source routing -> bazira se na pogrešno postavljeno mijesto firewalla
- upotreba pogrešnih checksumova -> služi da provjere jesu li podaci ispravno prenesi u mreži (--badsum)
    - ako na lošu sumu dobijemo odgovr IDS/IPS su loše konfigurirani
- slučajni odabir reda skeniranja -> (--hosts)
- anonimizeri ->
- stvaranje custom paketa -> najkompliciranija tehnika zbog koje moramo otkrivati i iskorištavati nove stvari (alati: Packet Crafting tool, Netcast)
 
#### Dobro bi bilo napraviti dijagram toplogije mreže