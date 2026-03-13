# KRIPTOGRAFIJA
 
#### Što je kriptografija
- konverzija podataka u nečitljiv kod koji se može sigurno prenosti preko nesigurnog kom kanala
 
### Ciljevi
- osigurati atentifikaciju
- povjerljivost
- integritet
- neporecivost
 
### Transpozicijski kod
- piše se tako da se slova abecede pomaknu u lijevo ili desno za određenu količinu slova
- smjer nije bitan ali ga mi možemo zapamtiti
- Rot cypher, Miscovsky cypher
 
### Substitution cypher
- blok teksta se mjen ja s nečitljivim tekstom
- koristi se algoritmi kriptiranja
- možemo doba se koristiti napredni mat. agloritmi za rane rezultate
 
### Moderne metode
1. Tip ključa
    - privatni ključevi -> isti ključevi za enkripciju i za deskripciju
    - javni ključevi -> različiti ključevi za enkripciju i deskripciju
2. Oblik ulaznih podataka
    - blok algoritam -> cilj je da se enkriptira blok teksta iste duljine
    - strubg algoritam -> kontinuirano kopiraju ulazni tekst (SEAL)
3. Simetrična i asimetrična enkripcija
    - za kriptiranje i dekripciju se koriste različiti ključevi
    - simetrični algoritmi koriste isti tajni ključ za enkripciju i dekripciju
 
### Ranjivosti
1. simetričan
    - pohrana ključeva
    - slanje ključeva
    - ne jamči autentifikaciju korisnika
    - ranjiva na napade riječnikom i brute fource napade
2. Asimetrična
    - spora obrada
    - ako izgubimo privatni ključ u problemu smo
    - ranjiva na man in the middle napade i bruit fource
 
### Snage
1. **Simetrične**
    - brže za implementaciju
    - zahtjeva manje procesorske moći
    - manje ranjive na globalnu sigurnost poruka
    - ključ nije vezan uz podatke i može se često mijenjati
2. Asimetrična
    - jednostavnija za upotrebuu jer joj netrebaju velike količine ključeva
    - osigurava neporecivost
    - omogućava autentifikaciju
 
### Algoritmi koji se koriste
1. DES
    - simetrični algoritam koji koristi blok od 64 bita i 56 bitne ključeve
    - 3DES -> 3 puta po 56 bitni ključ
2. AES (Advanced Encryption Standard)
    - simetrilni blok algoritam (128 bitova) i dinamičke ključeve (128-256)
    - služi za osjetiljivo ali otvorenog podatka
3. RC4, RC5
    - simetrični algoritmi
    - složeniji algoritmi zahtjevaju više procesorske moći
    - RC4 -> ranjiviji ali ne zahtjeva punu moć ima varijablini ključ za enkripciju prometa u mreži
    - RC5 -> blok algoritam
4. Bloatfish
    - dizajniran da bi zamenio DES
    - cilj je visoka učinkovitost i sigurnost
    - blok od 64 bita i ključ od 448 bitova
    - koristi se za osiguranje plačanja
5. Twofish
    - ključ do 256 biova
    - cilj je brzina korištenja
6. Threefish
    - ista veličina bloka i ključeva, a ključ može biti do 1024 bita
7. Serpent
    - 128 blok, 256 blok, Sličan AES-u
8. ITEA (Time enc alg)
    - 64 bitni blok, 128 bitni ključ
    - Napravljen zbog brzine, manje siguran
9. CAST
    - v128, v256
    - v128 ima 64 bitni blok i 128 bitni ključ
    - v256 ima 128 bitni blok i 256 bitni ključ
