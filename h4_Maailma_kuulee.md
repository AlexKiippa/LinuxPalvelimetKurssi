# H4 Maailma kuulee

## x)

Tämä artikkeli käsittelee ensimmäisiä vaiheita uuden virtuaalisen yksityispalvelimen määrityksessä DigitalOceanissa ja DNS-nimen määrityksessä NameCheapilla. Opastus sisältää ohjeita palvelimen luomisesta, tietoturva- ja käyttäjähallinnasta sekä ohjelmistopäivityksistä. Se mainitsee myös mahdollisuuden saada ilmainen GitHub-koulutuspaketti, joka sisältää virtuaalisen yksityispalvelimen ja verkkotunnuksen. Artikkelin tärkein viesti on käyttää vahvoja salasanoja ja varmistaa tietoturva asennettujen ohjelmistojen päivityksillä.

## a) 

Kirjauduin GitHub Educationin avulla DigitalOceaniin ja loin Dropletsin (Cloud serverin)

Ympäristöksi valitsin Debianin, koska se on sama mikä minun virtuaalikoneella ja sitä käytämme tunnilla.
<img width="817" alt="debian" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/7a01aabd-009c-406a-bf98-0c14cbafe47a">

Sitten valitsin halvimman prosessori (CPU) vaihtoehdon, koska kyseessä on vain pyörittää webbisivuja
<img width="848" alt="RegularSubs" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/591ecfa4-68cf-483e-8ccf-84bd00313fd6">

Viimeiseksi loin hyvin hankalan salasanan vaatimusten mukaan.
<img width="814" alt="salasana" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/6158eea3-d95e-428d-b812-05c4affd2152">

Ja näin minulla oli oma vuokrattu palvelin päällä: 
<img width="919" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/6c5be4be-7410-49ef-a598-718d7c1dcd52">

## b)

Ensinmäinen tehtävä oli kirjautua serverille:
> $ ssh root@206.189.98.149
<img width="398" alt="Serverille_Kirjautuminen" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/a27b9bba-a7a2-49a4-a030-b4818cbd1e70">

### Palomuuri

Seuraavaksi palomuurin päälle laitto ja reikä SSH:ta varten:
ufw palomuuri ei ollut ennestään asennettu joten se täytyi asentaa ensiksi:
> $ sudo apt-get update
> $ sudo apt-get install ufw

<img width="344" alt="palomuuri asennus" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/d05755ce-2c8a-46b3-b08f-7c3c2f35fd02">

Sitten tehtiin reikä SSH:ta sekä apachea varten valmiiksi ja sen jälkeen palomuuri päälle:
> $ sudo ufw allow 22/tcp
> $ sudo ufw allow 80/tcp
> $ sudo ufw enable

<img width="401" alt="Firewall Kolo" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/9392e7d0-6864-4df8-aa02-3d0184913b93">

### Käyttäjät

Loin uuden käyttäjän ja annoin sille sudo oikeudet:

> $ sudo adduser alexk
> $ sudo adduser alexk sudo

Avasin uuden terminaali ikkunan ja testasin kirjautumista uudella käyttäjällä:

> $ ssh alexk@206.189.98.149
<img width="393" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/f0f30573-29e3-4df4-a04c-16e7054e660d">

Seuraavaksi lukitsin root käyttäjän:
> $ sudo usermod --lock root:

<img width="335" alt="lock root" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/6da6b236-4ece-4748-b4fb-c3e43c2f2192">

Ja laitoin root kirjautumisen SSH:lla pois päältä muokkaamalla /etc/ssh/sshd_config tiedostoa ja lisäämällä rivin: "PermitRootLogin no"

> $ sudoedit /etc/ssh/sshd_config/

"PermitRootLogin no"

<img width="383" alt="permitlogin" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/7011499f-1b55-47d3-ba37-a73988430ea2">

Ja sitten uudelleen käynnistäminen
> $ sudo service ssh restart

<img width="356" alt="restart after lock" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/6d174c62-eee2-4a59-9e65-b1db3a980366">

### Ohjemiston päivitys

Pakettejen päivitys oli seuraava vaihe ja se onnistui kahdella komennolla:
> $ sudo apt-get update
> $ sudo apt-get upgrade
<img width="338" alt="Ohjelmistojenpäivitys" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/a30f5cff-8e83-4308-ba55-5ef12dcfbc25">

## c)

Webbi palvelimen asennus olikin jo entuudestaan tuttua viime tunnilta joten tämä kävi nopeasti.

1. Asennettiin Apache-web-palvelin:
> $ sudo apt-get update
> $ sudo apt-get install apache2
2. Käynnistetään Apache-palvelin ja asetetaan se käynnistymään automaattisesti käynnistyksen yhteydessä:
> $ sudo systemctl start apache2
> $ sudo systemctl enable apache2
3. Luodaan esimerkkisivu.

 Ensin navikoidaan itsemme html hakemistoon.
 
> $ /var/www/html/

Ja luodaan yksinkertainen HTML-sivu

> $ sudo nano index.html

Koska index.html tiedosto oli jo olemassa ja se sisälsi paljon html koodia jota oli työlästä muokata niin poistin sen ja loin uuden:

> $ sudo rm index.html
> $ sudo nano index.html 
<img width="365" alt="Poisto ja uusi sivu" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/24f33bd6-337a-4b6b-a46f-bfde35ef766f">

Sitten kirjoitin tosi yksinkertaisen HTML sivun ja tallensin:

<img width="360" alt="HTMLKOODI" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/143047f2-99e7-43ee-9694-3fb02c3d7653">



4. Ja esimerkki sivu näkyi hienosti julkisesta IP-osoitteesta.

<img width="529" alt="Testin sivu" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/71920100-8c6b-4bd8-a92e-93d08942c5a1">

## d)

Avasin lokin josta pystyin tarkastelemaan murtautumisia:

> $ journalctl -n 2000; journalctl --since today

<img width="412" alt="komento murtautumis" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/929c3451-a72e-44e1-b88d-80894ba1e63c">

Lokissa palomuuri oli blockannut 4 eri yritystä tai ohjelmaa "[UFW BLOCK]. Tämä ei välttämättä ole suora murtautumisyritys, mutta se osoittaa, että palomuuri on havainnut ja estänyt tietyn verkkoliikenteen.

<img width="943" alt="murtautumis" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/d3ec00c0-5865-401f-96fe-8610fdf90b95">

## Lähteet
- https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/
