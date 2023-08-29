# h1 - Oma Linux

## x) 

## Raportin kirjoittaminen
- Artikkeli antaa ohjeet tehokkaaseen tietokonetestien raportointiin.
- Ohjeet sisältävät tarkan dokumentoinnin, toistettavuuden, ympäristötiedon, komentojen ja tapahtumien kvaamisen, odottamattomien tulosten rapostoinnin sekä viittaamisen lähteisiin.
- Lisäksi korostetaan rehellisyyttä, tekinoikeuksien huomioimista ja vakiotekstien käyttöä.

## FSF: FSF Free Software Definition

 "Vapaa ohjelmisto" tarkoittaa ohjelmistoa, joka myöntää käyttäjille vapauden ajaa, kopioida, jakaa, opiskella, muokata ja parantaa sitä. Se korostaa vapautta, ei hintaa, verraten "vapaata" ennemmin "vapaaseen puheeseen" kuin "ilmaiseen olueeseen". Termiä "libre-ohjelmisto" käytetään joskus osoittamaan vapautta eikä hintaa.

Neljä oleellista vapautta vapaassa ohjelmistossa ovat:

    - Vapaus ajaa mitä tahansa tarkoitusta varten.
    - Vapaus tutkia ja muokata, edellyttäen pääsyä lähdekoodiin.
    - Vapaus jakaa muuttamattomia ja muokattuja kopioita.
    - Vapaus jakaa muokattuja versioita.


# a) Linuxin asennus virtuaalikoneeseen

Ensin latasin Oracle Virtual Boxin sivulta: https://www.virtualbox.org/wiki/Downloads ja asensin. 
Seuraavaksin latasin ISO kuvan linuxin asennusta varten osoitteesta: https://cdimage.debian.org/debian-cd/current-live/amd64/iso-hybrid/debian-live-12.1.0-amd64-xfce.iso

Asennuksessa:

Virtual boxissa valittiin "New" ja sitten virtuaali koneen nimi kirjoitettiin ja valittiin "ISO Image" kohtaan juuri ladattu debian ISO tiedosto. Myös boxi "Skip unanttended Install" valittiin.

<img width="698" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/75e12a5b-e846-427b-921c-c06a3e3b9d40">

Hardware kohdassa valitsin muistia 4000 MB ja 4 CPU prosessoria.

<img width="688" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/507c6477-66f5-4cd9-8ade-af959a87afbf">

Sitten käytettiinkin oletus arvoja muissa kohdissa ja lopuksi painettiin "Finish".

<img width="688" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/d7a36c78-a0b9-44f3-8c5c-8c70f4131e13">

Tämän jälkeen käynnistettiin virtuaalinen kovalevy joka myls käynnistää ISO tiedoston. Valittiin sitten vaihtoehdoista Live system (amd64)

![image](https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/384b5fac-4c39-4a95-8e54-328d8c1c462d)

Seuraava vaihe olikin luoda repository jonne oli mahdollista luoda raportti kurssia varten ja tämä onnistui hyvin toimivalla netti yhteydellä virtuaali koneessa.

<img width="595" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/e22155f7-3d4c-4fbf-861c-703bcdc69f85">





## Lähteet:
https://terokarvinen.com/2023/linux-palvelimet-2023-alkusyksy/#h1-virtuaali-linux
