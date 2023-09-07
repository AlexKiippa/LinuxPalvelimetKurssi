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








## Lähteet
:https://terokarvinen.com/2008/05/02/install-apache-web-server-on-ubuntu-4/
