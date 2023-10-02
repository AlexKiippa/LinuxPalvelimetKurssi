# x)

## Palvelinpään weppiohjelmoinnin edut
- Webbi-sovellus toimii jokaisella järjestelmällä ja asentamatta mitään.
- Käytät aina uusinta versiota
- Web-sovellus kerää tietoa itsestään miten sitä käytetään

## Django 4 Instant Customer Database Tutorial
- Asenna Linux ja varmista yhteensopivuus.
- Luo virtuaaliympäristö ja aktivoi se.
- Asenna Django ja muut riippuvuudet.
- Luo Django-projekti ja käynnistä kehityspalvelin.
- Hallitse projekteja admin-käyttöliittymässä.
- Varmista tietokannan toiminta ja luo admin-käyttäjä.
- Mukauta mallien näyttöä tarvittaessa

## Deploy Django 4 - Production Install
- Päivitä pakettien metatiedot: sudo apt-get update
- Asenna Apache-palvelin: sudo apt-get -y install apache2
- Luo uusi Django-projekti.
- Lisää projektillesi Apache-konfiguraatio tiedostoon /etc/apache2/sites-available/teroco.conf. Muista mukauttaa tiedostopolut.
- Ota uusi verkkosivusto käyttöön ja poista tarpeettomat.
- Asenna Apache WSGI -moduuli: sudo apt-get -y install libapache2-mod-wsgi-py3
- Käynnistä Apache uudelleen: sudo systemctl restart apache2
- Tarkista, että Apache palvelee Django-projektiasi selaimessa.
Näillä ohjeilla saat Django-websovelluksen toimimaan Apache-palvelimen kanssa Linuxissa

# a)

### Django on Python-pohjainen joten ensin täytyy asentaa python.
>$ sudo apt-get update

>$ sudo apt-get install python3
<img width="342" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/db024d64-6709-494c-846d-8e1a0f6191c5">

### Seuraavaksi asennetaan Pip joka on pythonin paketinhallintajärjestelmä.

>$ sudo apt-get intsall python3-pip
<img width="349" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/d0a07b4f-5690-4faf-a9dc-1b9d1e0c39d0">

### Luodaan ja aktivoidaan virtuaaliympäristö.

> python3 -m venv myenv

> source myen/bin/activate

<img width="278" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/bf19aede-d9e9-4a43-81cd-322a2f44e08e">


### Sitten asennetaan Django:

> pip install django
<img width="363" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/1586f1c1-d158-4fc1-ae56-20758db982ca">


### Luodaan Django-projekti ja siirrytään projektikansioon

>django-admin startproject linuxpalvelimet

>cd linuxpalvelimet

<img width="404" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/e493c367-1f10-4cf1-99a6-75501339c45b">

### Käynnistetään kehityspalvelin ja tarkistetaan esimerkki sivut.

Käynnistetään kehityspalvelin
>./manage.py runserver

Varoittelin vähän käynnistäessä "unapplied migrations", mutta palvelin meni käyntiin.

<img width="393" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/358de169-305f-44fe-b600-e888d12d79a3">

Ja osoitteessa 'http://127.0.0.1:8000/' näkyi Django-esimerkkisivu.

<img width="648" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/9fc69a93-08c1-4ca8-9bba-35b38416e8d4">


# b) 

### Luotuun Django-projektiin määritellään malli ja rekisteröidään malli admin-liittymään.

Luodaan models.py tiedosto 
> $ nano linuxpalvelimet/models.py

Määritellään yksinkertainen malli käyttäjille

<img width="254" alt="MallinMäärittely" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/a8e7b81d-0900-49a7-b8fc-3b4fa9cbdc15">

### Luodaan admin.py tiedosto ja rekisteröidään admin-liittymä
>$ nano linuxpalvelimet/models.py

Tiedoston sisältö:
<img width="257" alt="RekisteröidäänMalli" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/af505221-3d92-44fa-96e4-b710ccb5cf25">

### Luodaan ja sovitetaan tietokanta ja luodaan admin-käyttäjä
>$ python manage.py makemigrations

>$ python manage.py migrate

<img width="428" alt="Sovitetaan tietokanta" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/c0e077e9-5b75-4c06-a576-56dc7e87c414">

Admin-käyttäjän luonti.

>$ python manage.py createsuperuser

<img width="422" alt="Luodaan adminkäyttäjä" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/ef12333a-47a1-49cb-b8ec-6c5c60598c2e">


### Käynnistetään palvelin ja kirjaudutaan admin-liittymään.

Palvelin käynnistys 
>$ python manage.py runserver

Selaimessa osoitteessa 'http://127.0.0.1:8000/admin/' kirjaudutaan sisään juuri luodulla käyttäjällä.

<img width="527" alt="Kirjaudutaan sisään" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/f74bfafc-71d0-4497-abbe-3eb0ca0b4b3f">

Admin-liittymässä näkyy users kohta josta onkin sitten mahdollista lisälläi uusia käyttäjiä tietokantaan.

<img width="398" alt="adminLiittymä" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/f57501d9-9e87-4d9e-817b-ed5f7984cae8">

# c)


### Asennetaan virtualenv ja luodaan uusi VirtualEnv

>$ sudo apt-get -y install virtualenv 

>$ cd publicwsgi/

>$ virtualenv -p python3 --system-site-packages env

<img width="418" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/b00c811f-3e19-467d-b41e-941d2ae0b8ff">

### Asennetaan Django virtualEnv:iin


Hypätään virtualenv:n

>$ source env/bin/activate

Luodaan teksitiedosto jossa lukee "django" ja ladataan Django sen kautta

>$ micro requirements.txt

>$ pip install -r requirements.txt

<img width="383" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/ff742a72-1652-4af6-b97a-172387656a75">

### Uusi Django projekti

Muokataan alexco.conf tiedosto

>$ sudoedit /etc/apache2/sites-available/alexco.conf

<img width="523" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/caa749e9-fc38-434f-8a86-9a95e16f0ee4">

Sitten asennetaan **WSGI** moduuli
>$ sudo apt-get -y install libapache2-mod-wsgi-py3

Tsekataan .conf tiedosto config testillä

>$ /sbin/apache2ctl configtest


<img width="369" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/99b77caa-055b-4b71-9a5c-d027cb967357">

**Syntax OK**

Käynnistetään apache uudelleen ja katsotaan miltä localhost näyttää:

>$ sudo systemctl restart apache2

<img width="315" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/bcb45917-840f-4ed1-9403-73e6b5a2856a">

localhost ei näyttänyt hyvältä ja monen tunnin korjailun jälkeen saanut sivua näkymään..






