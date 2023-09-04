# Komentaja pingviini

## x) Command Line Basics Revisited

- Linuxin ja BSD:n käyttämä komentorivi on kestänyt aikakausia, se oli olemassa ennen Googlea, verkkosivuja, Linuxia, Windowsia ja jopa internetiä. Se pysyy kätevänä, nopeana, ilmaisuvoimaisena ja helposti automatisoitavana.
- Työhakemisto voidaan tarkistaa 'pwd'-komennolla. Tiedostonhallintakomennot sisältävät 'ls'-komennon tiedostojen luetteluun, 'cd'-komennon hakemiston vaihtamiseen, 'mv'-komennon tiedostojen siirtämiseen tai nimeämiseen ja 'rm'-komennon tiedostojen ja hakemistojen poistamiseen.
- SSH-etähallinta mahdollistaa turvallisen etäyhteyden, ja käyttäen 'scp'-komentoa tiedostoja voidaan kopioida turvallisesti etäkoneille. Lisäksi käsitellään 'man'-käskyä ohjeiden lukemiseen, välilyöntiä komentorivin täydentämiseen ja historian selaamiseen, sekä 'sudo'-käskyä ja paketinhallintaa ohjelmistojen asentamiseksi.

## a) Micro
 Micron asennus onnistui komennolla "curl https://getmic.ro | bash
 
<img width="407" alt="Micro install" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/1b696142-5a2f-48b8-a127-04580db9f9a9">

## b) Rauta

lshw asennus onnistui komennolla " sudo apt install lshw-gtk"

<img width="377" alt="lshw install" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/8ed215c7-9cdb-49f5-9dac-44b226de9331">

Komento "sudo lshw -short -sanitize" listaa lyhyen ja sensoroidun yhteenvedon laitteiston tiedoista. 

<img width="502" alt="Lshw " src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/e20fd797-69ee-4303-8c05-ed0564b6c66f">

Listatut tiedot ovat hyvä yleiskäyttöön ja jaettavaksi, koska ne eivät paljasta mitään arkaluonteista tietoa.

## c) Apt

Kolme komentorivihojelmaa jotka asensin Linuxille olivat: htop, Neofetch ja Midnight Commander. 

Apt-get komento jolla olisi saanut asennettua kaikki ohjelmat kerralla olisi ollut "sudo apt-get install htop neofetch mc"

### Htop

Ensin asennettiin htop komennolla "sudo apt-get install htop"

<img width="437" alt="hTopAsennus" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/875a474e-dde6-4e41-a32d-cd3414b6da32">

Sitten komennolla "htop" käynnistettiin htop

Htop tarjoaa kattavan näkymän järjestelmän suorituskyvystä ja prosesseista.

<img width="957" alt="Htop kuva" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/48854744-7d62-4afd-8186-bced7bb2d246">

### Neofetch

Neofetchin asennus onnistui myös helposti komennolla "sudo apt-get install neofetch" sekä komennolla "neofetch" pystytään Neofetchiä käyttämään.

<img width="482" alt="neoFetch" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/e5d07327-8baf-4a57-bfb3-70222aa34a40">

Neofecth näyttää järjestelmän tiedot ja hienon logon terminaalissa

### Midnight Commander (mc)

Asennus komento: "sudo apt-get install mc"
Käynnistys komento: "mc"

<img width="955" alt="mc" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/cf5a0170-5e70-4db0-a30c-9a9725232a33">

Midnight Commander on tekstipohjainen tiedostonhallintaohjelma, joka tarjoaa monipuolisen käyttöliittymän tiedostojen hallintaan.

## d) 

1. **/** (Juurihakemisto)
   Tämä on juurihakemisto, joka on tiedostojärjestelmän ylimpänä tasona. Kaikki muut
   hakemistot ovat tämän alla.

<img width="338" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/61939ec4-5774-443c-ae87-42700f228e1b">

   
2. **/home/**

Tämä hakemisto sisältää kotihakemistot kaikille järjestelmän käyttäjille.

<img width="191" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/2c12cbf5-ab4b-47ff-a5f2-f9d52e10647e">

3. **/etc/** (Järjestelmän asetukset)

Tämä hakemisto sisältää järjestelmätason asetustiedostot, jotka ovat yleensä ihmisen luettavissa olevia tekstitiedostoja.

<img width="538" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/1498c019-e885-4ec4-92ec-cf7bd64472b3">

4. **/media/**(Irroitettavat välineet)

Tämä hakemisto sisältää liitetyt irrotettavat välineet, kuten CD/DVD-levyt tai USB-tikut.

<img width="335" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/5aea7610-a6bd-490c-bcbf-bd8d177a610c">

Ja koska mitään media laitteita/välineitä ei ole kytketty niin "ls" ei palauta mitään, koska hakemisto on tyhjä. 

5. **/var/log/** (Lokitiedostot)

Tämä hakemisto sisältää järjestelmätason lokitiedostot, joissa on tärkeitä tietoja järjestelmän toiminnasta ja vioista.

<img width="758" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/12cf4927-8185-4cc3-af21-487dac00ad19">


## e) Grep

Komento "grep rivi kissa.txt" luettelee kaikki rivit tekstitiedostossa jossa esiintyy sana "rivi".

<img width="359" alt="GrepEsim_1" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/00f81c19-8209-4835-a0ad-dc648708d3b6">

Komento "grep -v rivi kissa.txt" luettelee sen sijaan kaikki rivit jossa sana "rivi ei esiinny. Tämä komento on myös kirjankoko tarkka eli jos sanassa on isoja kirjaimia niin palauttaa se silti kyseisen rivin.

<img width="417" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/6bab6e43-b871-4524-9557-1185e0857e19">


## f) Pipe

Kuinka monta kertaa tietty sana esiintyy tiedostossa. '**grep**'-komento tulostaa rivit jossa sana esiintyy ja sen voi putkea '**wc**'-komennon syötteeseen (word count).
Eli kun komento 'grep rivi kissa.txt | wc -l' syötetään grep komento putkea tulosteen word countteriin joka laskee sanojen määrän tiedostossa.

<img width="369" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/daa4ea63-51e7-4dd6-82de-449e17c0b6a8">

## g) Tukki



## Lähteet:
https://terokarvinen.com/2023/linux-palvelimet-2023-alkusyksy/#h1-virtuaali-linux
https://terokarvinen.com/2020/command-line-basics-revisited/?fromSearch=command%20line%20basics%20revisited
