#H5 Nimittäin

## x)

###  New Default Website with Apache2


Tämä opastus näyttää, kuinka luoda perusverkkosivusto Apache2-palvelimelle:

1. Asenna Apache: sudo apt-get install apache2.
2. Poista oletussivu käytöstä: sudo a2dissite 000-default.conf.
3. Luo mukautettu VirtualHost-määritys: /etc/apache2/sites-available/tero.conf.
4. Ota mukautettu VirtualHost käyttöön: sudo a2ensite tero.conf.
5. Käynnistä Apache uudelleen: sudo service apache2 restart.
6. Luo yksinkertainen HTML-kotisivu osoitteeseen /home/tero/public_html/index.html.
7. Avaa verkkosivusto osoitteessa http://localhost.

### Name Based Virtual Hosts on Apache

1. Asenna Apache-verkkopalvelin: sudo apt-get -y install apache2.
2. Luo uusi nimeen perustuva virtuaalihostaus.
3. Luo verkkosivu tavallisena käyttäjänä.
4. Testaa sivusto curl-komennolla.
5. Simuloi nimen palvelua lisäämällä /etc/hosts-tiedostoon.
6. Testaa sivusto selaimella osoitteissa http://localhost ja http://nimesi.example.com.
7. Tämä mahdollistaa useiden verkkosivustojen isännöinnin samalla IP-osoitteella Apache-verkkopalvelimella.

### Name-based Virtual Host Support


Nimipohjaisessa virtuaalihostauksessa useat verkkotunnukset voivat jakaa saman IP-osoitteen, mikä säästää IP-osoitteiden käyttöä ja tekee konfiguroinnista yksinkertaisempaa. Jokainen verkkotunnus määritellään <VirtualHost> -lohkossa, joka sisältää ServerName- ja DocumentRoot-ohjeet. Oletusvirtuaalihosti käsittelee pyyntöjä, jotka eivät vastaa muihin määriteltyihin virtuaalihosteihin. On suositeltavaa aina määrittää ServerName jokaiselle virtuaalihostille, ja voit lisätä muita nimiä ServerAlias-ohjeella. Nimipohjaisten virtuaalihostien järjestys määräytyy niiden esiintymisjärjestyksen perusteella, ja ensimmäinen sopiva ServerName tai ServerAlias otetaan käyttöön.


## a) 

Sivulla "NameCheap.com" kirjoitin haluamani domain-nimen hakukenttään
<img width="755" alt="1" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/9341b497-8af5-4975-b864-23960c81ba0e">

Näin opiskelijana etsin halvimman domain-nimen joka oli saatavilla ja se oli "alex-kiippa.wiki". Lisäsin sen koriin ja täytin maksutiedot ja ostin domain-nimen.

<img width="889" alt="2" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/da34c4e3-8f6f-4891-9ebd-99cf6d412baa">

Ja maksettua näin minulla oli oma domain-nimi.

<img width="824" alt="3" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/9a5e41e9-af8b-4c23-b64f-8df26e38b3d6">


Sitten navigoin NameCheap:ssä Domain listiin ja valitsin juuri ostamani Domainin.

<img width="1081" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/e0db95ec-801f-4a50-935e-d35a6c0c129d">

Advance DNS tabissa muokkasin tiedot siten, että sijoitin ip osoitteen jolla serverini pyörii DigitalOceanissa.

<img width="845" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/d070be06-e6bf-4087-b91f-357a1b3ce8af">


<img width="537" alt="5" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/404ba56f-bf99-44c4-8bf3-c30e85134b7f">


Seuraavaksi muodostettiin yhteys serverille
> $ ssh alexk@206.189.98.149

<img width="368" alt="LogIN_6" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/8616abd4-2f71-45c9-b9f6-70e786c6238c">

Loin simppelin HTMl tiedoston ja hakemiston.
> $ sudo nano /var/www/alex-kiippa.wiki/index.html

Tämän jälkeen loin virtual host conf tiedoston.
> sudo nano /etc/apache2/sites-available/alex-kiippa.wiki.conf
<img width="402" alt="Conf7" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/24ab4e71-1efa-464e-9be4-4a37ff47b589">

Conf tiedoston sisältö näytti tältä:

<img width="398" alt="VirtualHOst" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/414dcf8c-5ee8-434f-b34e-85d7f48fb7bf">

Lopuksi virtual hostin enable ja reload apache
> $ sudo a2ensite alex-kiippa.wiki.conf

> $ sudo systemctl reload apache2

Lisäsin myös domain nimen DigitalOcean sivuille.
<img width="905" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/b1bd4de9-ada7-47f6-9478-ca2c65d35905">

Ja loin DNS recordin domainille: 

<img width="922" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/87ea2143-d7f8-4eb1-9825-a46e2472b080">




## Lähteet
https://terokarvinen.com/2018/04/10/name-based-virtual-hosts-on-apache-multiple-websites-to-single-ip-address/
https://httpd.apache.org/docs/2.4/vhosts/name-based.html
https://terokarvinen.com/2016/02/16/new-default-website-with-apache2-show-your-homepage-at-top-of-example-com-no-tilde/



