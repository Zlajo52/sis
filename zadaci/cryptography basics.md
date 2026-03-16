# Cryptography basics
* **Kriptografija** služi za **sigurnu komunikaciju u prisutnosti napadača**.
* Osigurava tri glavne stvari: **povjerljivost (confidentiality), integritet (integrity) i autentičnost (authenticity)** podataka.
* Cilj je da **neovlaštene osobe ne mogu pročitati ili izmijeniti poruke**.

**Primjeri korištenja kriptografije:**

* **Prijava na web stranice** – lozinke se šalju **šifrirane**.
* **SSH konekcija** – stvara **šifrirani tunel** između klijenta i servera.
* **Online bankarstvo** – provjera **certifikata servera** kako bi se potvrdilo da je pravi
* **Preuzimanje datoteka** – koriste se **hash funkcije** za provjeru da datoteka nije izmijenjena

**Zakoni i sigurnosni standardi:**

* **PCI DSS** – standard za sigurnost podataka kreditnih kartica (šifriranje podataka **u pohrani i tijekom prijenosa**)
* Za **medicinske podatke** postoje zakoni poput:

  * **HIPAA** i **HITECH** (SAD)
  * **GDPR** (EU)
  * **DPA** (UK)
---
* **Plaintext** – originalna, čitljiva poruka ili podatak prije šifriranja (npr. tekst, slika, kartični podaci)
* **Encryption (šifriranje)** – proces pretvaranja plaintexta u **ciphertext** pomoću **ciphera (algoritma)** i **ključa**.
* **Ciphertext** – nečitljiva, šifrirana verzija poruke
* **Cipher** – algoritam koji pretvara **plaintext ↔ ciphertext**
* **Key (ključ)** – niz bitova koji se koristi za šifriranje i dešifriranje; **mora ostati tajan**
* **Decryption (dešifriranje)** – proces vraćanja **ciphertexta natrag u plaintext** pomoću ključa
---
* Jedan od najjednostavnijih povijesnih sustava je **Caesar Cipher**

**Kako radi Caesarova šifra:**

* Svako slovo u poruci **pomakne se za određeni broj mjesta u abecedi**
* Primjer:

  * Plaintext: **TRYHACKME**
  * Key: **3**
  * Ciphertext: **WUBKDFNPH**
* Kod **šifriranja** slova se pomiču **udesno**, a kod **dešifriranja** **ulijevo**

**Sigurnost:**

* Postoji samo **25 mogućih ključeva** (jer abeceda ima 26 slova)
* Zbog toga je šifra **lako razbijiva brute-force napadom** → danas se smatra **nesigurnom**

**Drugi poznati povijesni sustavi:**

* **Vigenère cipher** (16. stoljeće)
* **Enigma machine** (Drugi svjetski rat)
* **One-time pad** (razdoblje Hladnog rata)
---
### **Dva glavna tipa enkripcije:**

1. **Symmetric Encryption (simetrična enkripcija)**

   * Koristi **isti ključ za šifriranje i dešifriranje**.
   * Ključ mora ostati **tajan** i sigurno se dijeliti između sudionika.
   * Problemi: teško dijeljenje ključa, posebno ako je mnogo primatelja ili postoji moćan napadač.
   * Primjeri:

     * **DES** – 56-bitni ključ, probijen 1999.
     * **3DES** – DES primijenjen tri puta, 168-bitni ključ, efektivna sigurnost 112 bitova, zastarjelo.
     * **AES** – standard od 2001., ključevi 128, 192 ili 256 bitova.

2. **Asymmetric Encryption (asimetrična enkripcija)**

   * Koristi **par ključeva**:

     * **Public key** – za šifriranje (može se dijeliti javno)
     * **Private key** – za dešifriranje (mora ostati tajan)
   * Prednosti: rješava problem sigurnog dijeljenja ključa.
   * Nedostatci: sporija od simetrične, zahtijeva **dulje ključeve**.
   * Primjeri: **RSA, Diffie-Hellman, ECC**

     * ECC: kraći ključevi, ali jednako siguran kao duži RSA ključevi.
---
### **Matematičke osnove kriptografije:**

1. **XOR operacija (⊕)**

   * Logička operacija u binarnoj aritmetici.
   * Pravilo:

     * 0 ⊕ 0 = 0
     * 0 ⊕ 1 = 1
     * 1 ⊕ 0 = 1
     * 1 ⊕ 1 = 0
   * Svojstva:

     * **A ⊕ A = 0**
     * **A ⊕ 0 = A**
     * Komutativna: A ⊕ B = B ⊕ A
     * Asocijativna: (A ⊕ B) ⊕ C = A ⊕ (B ⊕ C)
   * Primjena u kriptografiji: jednostavna simetrična enkripcija:

     * **C = P ⊕ K** (ciphertext)
     * Dešifriranje: **P = C ⊕ K**

2. **Modulo operacija (%)**

   * Daje **ostatak pri dijeljenju**: X % Y = ostatak pri dijeljenju X s Y.
   * Primjeri:

     * 25 % 5 = 0
     * 23 % 6 = 5
     * 23 % 7 = 2
   * Svojstva:

     * Rezultat je uvijek **ne-negativan i manji od djelitelja**.
     * **Nije reverzibilna** – za x % n = r postoji beskonačno mnogo rješenja.
   * Važno za rad s **velikim brojevima u kriptografiji**; često se koristi u algoritmima javnog ključa.
