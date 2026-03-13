# Skeniranje mreže
 
- skup procedura za identifikaciju cvorova portova i usluga u mreži
- ciljevi: otkriti čvorove, adrese i portove
- otkriti arhitekturu i os čvorova
- otkriti uloge koje su dostupne na čvorovima
- otkriti ranjivosti u čvorovima
 
#### Postoje 3 vrste skeniranja:
1. skeniranje mreže -> ciljevi: otkriti čvorove, adrese i portove
2. skeniranje portova -> ciljevi: spajanje ili testiranje tcp ili udp portova s ciljem otkrivanja usluga na čvorovima
3. skeniranje rajnivosti -> ciljevi: provjera je ili sustav moguće iskoristiti na temelju pronađenih ranjivosti
 
### Za uspješno sekniranje moramo znati protokole:
1. TCP -> osigurava pouzdanost mreže
2. UDP -> brži ali manje siguran
 
![alt text](image.png)
 
- najvažniji paketi TCP-a: SYN, ACK, RST, PSK (direktno šalje paket aplikaciji)
 
## Alati za skeniranje mreže
1. Nmap -> najpoznatiji alat za skeniranje mreža
2. MechaSploit -> najpoznatiji alat za skeniranje i iskorištavanje ranjivosti
3. Hping2 / Hping3 -> naprednija verzija ping alata
4. MegaPing
 
### Otkrivanje živih računala
1. ARP ping scan -> najpouzdanijih metoda otkrivanja hostova, najefikasnija (potpun je otvoren, -PR)
2. UDP ping scan -> dobar ako imamo TCP filtering, jer daje bolje rezultate (-PU)
3. ICMP ping scan -> koristi se za testiranje dal u mreži postoji firewall (-PE)
4. TCP ACK ping scan -> (-PA)
5. SYN ping scan -> očekujemo ACK odgovor (ako ga dobijemo onda je živ ako ne nije živ) (-PS)
 
### Skeniranje portova
1. TCP connect / Full open scan -> otvaramo i zatvaramo ful vezu i automacki zatvorimo (vrlo lako se otkrivaju), često se blokiraju u mreži (-sT)
2. Stelth scan / Half open scan -> ne uspostavimo do kraja vezu nego nakon SYN ACA pošaljemo reset (-sS)
3. Inverse TCP flag scan -> pomoću zastavica pokušđavamo otkirti jeli kod živ
    - podvrste null scan
    - fin scan
    - Christmas scan
    - maimon scan -> kad su fin i ack postavljeni
    - ACK flag -> šalje se neočekivani paketi i očekuju se TTL ili RST paket (koristi se -TTL i -sW -sA)
    - UDP scan -> ako ništa ne dobijemo nazad pretpostavljamo da je port otvoren (-sU), a ako nešto dobijemo port je sigurno zatvoren (koristimo ga da nadopunimo druge scanove)
    - LIST scan -> (-sL) zadužen da nam izgenerira sve ip-eve u subnetu i koriste reverse-DNS da ih identificiramo
    - IPv6 -> (-6)
    - SSDP -> Simple service discovery protocl, korsiti se uz UPMP (universal plug and play), radi se skeniranje
    - -sv -> opcija koja otkriva verije portova u pozadini
    - SCTP -> Stream Controll Transport protocol, ima specifične vrste paketa (-sY)
 
### Protumjere skeniranju portova
1. Firewall, IDS (ispravno ih konfigurirati)
2. redovito skeniranje vlastite mreže
3. ispravno konfigurirani switchevi i ruteri (postavljanje sigurnosnih postavki)
4. Firmwere mora biti ažuran
5. ICMP protokol (ispravno filtriranje)
6. ostaviti otvorene samo portove koji su potrebni za rad