# h3

## x)

1.Lataa Apache
Käytä tätäkomentoa asentaaksi Apache:
> $ sudo apt-get install apache2
2. Testaa Apache
Varmista Apachen asennus lokaalisesti:
> $ firefox "http://localhost"
3. Ota käyttöön käyttäjien kotisivut
userdir modulen käyttöön otto
> $ sudo a2enmod userdir
Käynnistä uudelleen Apache
> $ sudo systemctl restart apache2
4. Testaa käyttäjän kotisivu
Luo '**public_html**' kansio koti directoryyn ja mene selaimella osoitteeseen '**http://localhost/~yourname**'

Näillä ohjeilla sinulla on Apache asennettu ja käyttäjän kotisivut laitettu päälle. Tämä mahdollistaa sinun julkaista web kontenttia koti hakemistostasi


## a)
Apachen asennus onnistuu komennolla:
> $ sudo apt-get install apache2
<img width="368" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/65f23f30-e8c5-4c81-8a91-b9a5923811bf">
Apache oli jo entuudestaan asennettu tunnilla käydyn esimerkin ansiosta niin tämä komento ei asentanut, mitään uutta tällä kertaa.


Seuraavaksi testataan, että apache toimii lokaalisesti.
Komento:
> $ firefox "http://localhost"
<img width="372" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/62998124-65d7-4964-a1ce-8f7dddd702ab">

Komento sen jälkeen avaa firefoxin osoitteella 'localhost'
Tätä voi myös testata avaamalla selaimen ja kirjoittamalla hakukenttään 'localhost'

<img width="730" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/90edb78a-df4f-4f8e-821f-934720d2df20">

Kuvankaappauksessa sivu kertookin, että tämä Apache2 Debian oletussivu ja sivu toimii.

## b)

Lokiin päästiin hakemistosta
> $ cd var/log/
Ja komennolla
> $ sudo cat apache2/access.log

<img width="926" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/a9868d0f-866f-4134-a5fb-400e93b16d9b">


- 127.0.0.1: Käyttäjän tai asiakkaan IP-osoite.
- '- -': Kaksi viivaa, jotka edustavat käyttäjätunnusta ja tunnussanaa (nämä ovat yleensä tyhjiä HTTP-pyynnöissä).
- [04/Sep/2023:14:30:45 +0000]: Aikaleima, joka kertoo, milloin pyyntö tehtiin.
- "GET /index.html HTTP/1.1": HTTP-pyyntö, mukaan lukien käytetty metodi (GET), pyydetyt sivun polku (/index.html) ja HTTP-protokolla (HTTP/1.1).
- 200: Vastauksen tilakoodi (esim. 200 tarkoittaa "OK").
- 3380: Vastauksen koko tavuina.
- "-" "Mozilla/5.0 (X11; Linux x86_64; rv:102.0) Gecko/20100101 Firefox/102.0": Käytetty selain ja sen versio.

## c)
Esimerkkisivu löytyy hakemistosta 'var/www/html/index.html'
Tiedosta ei pysty teksiteditorilla muokata joten se pitää suorittaa terminaalin kautta. Esimerkki komento jolla voidaan haluamansa teksti tiedostoon joka näkyy kotisivulla:
> $ echo moikka|sudo tee /var/www/html/index.html
<img width="377" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/101c5683-e9f1-42d6-be20-2609aa4866f3">

Kuvassa olin jo hakemistossa joten jätin tiedoston juurihakemistot pois komennosta.
Sitten avattiin kotisivu ja katsottiin tuliko annettu teksti näkyviin kotisivulle.
> $ firefox localhost
<img width="349" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/1c8754ec-614b-4c3b-b061-2aca4afaf505">

## d)

Ensin Loin hakemistoon: /alexk/public_html/index_html tiedoston.
Ja tein simppelin html pohjan.

<img width="413" alt="EsimSivut" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/a0cf9d69-7816-4990-8a8d-d4a52c9c1f6e">


Varmistin, että 'userdir'-moduuli on käytössä:
> $ sudo a2enmod userdir


Ja käynnistin Apachen uudelleen:
> $ sudo systemctl restart apache2
<img width="323" alt="apache rest" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/737f8ebe-aaba-400f-a615-b176c7c45f53">

Sitten menin sivulle "localhost/~alexk" ja sivu näytti tältä:

<img width="305" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/2c439cf3-73f1-4bde-928f-3ae3400b4efe">


## e)
Validi HTML5 sivu tuli jo aikaisempaa tehtävää varten tehtyä, joten käytin sivua "validator.w3.org" tarkastamaan, että sivu oli oikeasti validi.

<img width="521" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/610f4a14-fddd-4908-96de-d0d0f4e2d7a6">

Ja validaattori näytti vihreää eli HTML5 sivu oli validi.


## f)

### curl -I

Tässä komento pyytää verkkosivustoa https://www.example.com ja tulostaa vain HTTP-otsikkotiedot.

> $ curl -I https://www.example.com


<img width="371" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/4bda6395-d3a5-403c-b21b-c6526f5494a1">

- HTTP/2 200: Tämä kertoo, että HTTP-vastauskoodi on 200, mikä tarkoittaa "OK". Sivusto on löytynyt ja vastaa pyyntöön onnistuneesti.

- content-encoding: gzip: Tämä osoittaa, että sivun sisältö on pakattu Gzip-koodauksella. Gzip-koodaus vähentää tiedoston kokoa ja nopeuttaa sen latautumista.

- accept-ranges: butes: Tämä osoittaa, että palvelin hyväksyy osittaisten sisältöpyyntöjen (range requests) käytön. Tämä voi olla hyödyllinen suurten tiedostojen lataamisessa osissa.
-age: 424419: Tämä osoittaa, että sivu on ollut välimuistissa 424419 sekuntia (noin 4,9 päivää). Välimuisti voi parantaa sivuston suorituskykyä, kun samat sivut toistuvasti pyydetään.

- cache-control: max-age=604800: Tämä määrittelee välimuistin säilyvyysajan sekunteina. Tässä tapauksessa sivu voidaan pitää välimuistissa enintään 604800 sekuntia (noin 7 päivää).

- content-type: text/html; charset=UTF-8: Tämä määrittelee sisällön tyypin ja merkistökoodauksen. Sisältö on HTML-muodossa käyttäen UTF-8 merkistökoodausta.

- date: sun 10 sep 2023 23:25:01 GMT: Tämä näyttää päivämäärän ja ajan, jolloin vastaus lähetettiin.

- etag: "3147526947+gzip": Tämä on entiteettiavain (entity tag), joka voi auttaa vertaamaan sivun versioita. Se voi auttaa välimuistissa ja päivitetyissä pyynnöissä.

- expires: Sun, 17 Sep 2023 23:25:01 GMT: Tämä osoittaa, milloin vastaus vanhenee ja ei ole enää kelvollinen välimuistissa.

- last-modified: Thu, 17 Oct 2019 07:18:26 GMT: Tämä kertoo, milloin sivu viimeksi muutettiin.

- server: ECS (bsa/EB18): Tämä kertoo palvelimen ohjelmiston ja version.

- x-cache: HIT: Tämä osoittaa, että pyyntö osui välimuistiin ja vastaus saatiin välimuistista (HIT tarkoittaa osumaa).

- content-lenght 648: Tämä ilmoittaa vastauksen sisällön pituuden tavuina, eli tässä tapauksessa sivun koko on 648 tavua.

### curl

> $ curl https://www.example.com


Tässä komento tekee saman HTTP-pyynnön, mutta tulostaa koko verkkosivun HTML-sisällön. Tämä komento lataisi koko HTML-sivun sisällön, kun taas curl -I tulostaisi vain otsikkotiedot.

<img width="775" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/5e57a1f4-20c1-40c1-88b6-0f6f049f5c95">


## m)

<img width="918" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/78c0aedb-2b4d-47bd-b927-69e8671d42fe">


## Lähteet
:https://terokarvinen.com/2008/05/02/install-apache-web-server-on-ubuntu-4/
