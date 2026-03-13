# Mrežni segmenti i podmreže (Subneti)

## Mrežni segment
Mrežni segment je skup računala povezanih istim fizičkim medijem.
Primjeri su Ethernet switch ili WiFi access point.
Ovo predstavlja fizičku povezanost uređaja.

## Podmreža (Subnet)
Podmreža je logička IP mreža.
Ima vlastiti raspon IP adresa i povezana je s ostatkom mreže putem rutera.
Predstavlja logičku povezanost.

## Vrste subnet maski
/16 (255.255.0.0) omogućuje oko 65 000 hostova.  
/24 (255.255.255.0) omogućuje oko 250 hostova.

# Otkrivanje aktivnih hostova (Host Discovery)

Cilj je otkriti koji su hostovi online kako se ne bi gubilo vrijeme na skeniranje neaktivnih IP adresa.

# Protokoli za otkrivanje hostova

## ARP – Link Layer
ARP se koristi samo unutar iste podmreže.
Traži MAC adresu za određeni IP.
Ako host odgovori, smatra se aktivnim.

Korisna komanda:
sudo nmap -PR -sn IP/24
                              
## ICMP – Network Layer
ICMP se koristi za pinganje hostova.
Često je blokiran firewallom.

ICMP Echo (ping):
sudo nmap -PE -sn IP/24

ICMP Timestamp:
sudo nmap -PP -sn IP/24

ICMP Address Mask:
sudo nmap -PM -sn IP/24

Ako nema odgovora, moguće je da firewall blokira ICMP.

## TCP SYN Ping – Transport Layer
Šalje TCP SYN paket (najčešće na port 80).
Ako host odgovori (SYN/ACK ili RST), host je online.

Korisna komanda:
sudo nmap -PS -sn IP/24

## TCP ACK Ping
Šalje TCP paket s ACK zastavicom.
Ako dođe RST odgovor, host je aktivan.

Korisna komanda:
sudo nmap -PA -sn IP/24

## UDP Ping
Šalje UDP paket.
Ako je port zatvoren, host vraća ICMP Port Unreachable poruku.

Korisna komanda:
sudo nmap -PU -sn IP/24

## Zadana Nmap logika
Na istoj mreži koristi ARP.
Izvan mreže koristi ICMP i TCP probe.
Neprivilegirani korisnik koristi TCP handshake.

## Isključivanje DNS rezolucije
Nmap po defaultu radi reverse DNS.

Isključi DNS:
nmap -n IP

Forsiraj DNS:
nmap -R IP

Postavi DNS server:
nmap --dns-servers 8.8.8.8 IP

## Masscan (brzo skeniranje)
Vrlo agresivan alat za brzo otkrivanje hostova.

Primjeri:
masscan IP/24 -p80
masscan IP/24 -p80,443
masscan IP/24 -p22-25
masscan IP/24 --top-ports 100


 