#Hello world

## y)
[Kotitehtävä-raportit](https://github.com/AlexKiippa/LinuxPalvelimetKurssi)
- [h1](https://github.com/AlexKiippa/LinuxPalvelimetKurssi/blob/main/h1-oma-linux.md)
- [h2](https://github.com/AlexKiippa/LinuxPalvelimetKurssi/blob/main/h2_Komentaja_pingviini.md)
- [h3](https://github.com/AlexKiippa/LinuxPalvelimetKurssi/blob/main/h3_Hello_Web_Server.md)
- [h4](https://github.com/AlexKiippa/LinuxPalvelimetKurssi/blob/main/h4_Maailma_kuulee.md)
- [h5](https://github.com/AlexKiippa/LinuxPalvelimetKurssi/blob/main/h5_nimitt%C3%A4in.md)
- [h6](https://github.com/AlexKiippa/LinuxPalvelimetKurssi/blob/main/h6_DJ_Ango.md)


## x)

### Tiivistelmä
- Koodin kääntäminen Javalla onnistuu:
>$ javac filename.java

- Koodin kääntäminen C:llä onnistuu:
>$ gcc filename.c

- Koodin kääntäminen Go:lla onnistuu:
>$ go build filename.go

[(Karvinen 2018)](https://terokarvinen.com/2018/hello-python3-bash-c-c-go-lua-ruby-java-programming-languages-on-ubuntu-18-04/)




## a)

Ensinmäinen vaihe on asentaa eri kielet.
>$ sudo apt-get update

Python:

>$ sudo apt-get install python3

Java

>$ sudo apt-get install default-jre default-jdk

C

>$ sudo apt-get install gcc

### Python
Luodaan ensin python tiedosto:
>$ nano hello.py

Sitten kirjoitetaan koodi joka tulostaa "Hei maailma" tekstin
<img width="158" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/0fd0aa7b-0a73-46dd-bade-760e08b4abd7">

Ja ajamalla komennon voidaan suorittaa koodi .py tiedostossa
>$ python3 hello.py

<img width="308" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/91b7cb0a-3495-4a13-915f-ee32d6ed365a">

### Java

Luodaan java tiedosto:

> nano HelloWorld.java

Kirjoitetaan koodi joka tulostaa tekstin "Hei maailma"

<img width="284" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/a9459fe1-182c-4a73-b60f-a527b779aa5b">

Ajetaan seuraavat komennot:

>javac HelloWorld.java

>java Helloworld

<img width="291" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/21fdead3-f223-44f1-a976-9e86fbb76f81">

### C

Luodaan tiedosto:

>$ nano hello.c

Kirjoitetaan koodi C:llä joka tulostaa "Hei maailma"

<img width="166" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/659429ed-10bc-433e-82dd-e56d560ba437">


Ajetaan seuraavat komennot terminaalissa:

>$ gcc -o hello hello.c

>$ ./hello

<img width="315" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/4fd74253-68e8-4009-b610-dd9dd9ced8e1">


## b)

### Hei maailma Javascriptillä (node.js)

Ensin asennetaan nodejs

> $ sudo apt-get update

>$ sudo apt-get install nodejs

Luodaan js tiedosto:

>$ nano hello.js


Kirjoitetaan koodi joka tulostaa "Hei maailma"

<img width="171" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/56144e10-55c0-4318-b337-f5a470e7ef92">

Ajetaan tiedosto komennolla:

>$ node hello.js

<img width="269" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/9a628325-db9b-4058-abf4-04590f5278a9">



## c)

Avataan interaktiivinen tulkkiympäristö

>$ python3

Nyt voidaan kirjoittaa matemaattisia laskutoimituksia ja Python-koodia suoraan tulkkiin ja näemme tulokset välittömästi:

<img width="106" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/b6bfdd72-e669-4b89-8faa-bb5e65acbf1b">


## d)

Luodaan shell tiedosto

>$ nano shell.sh

Kirjoitetaan shell scripti:

<img width="283" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/b9b2cc5a-0982-42f2-9faa-0e06893907e3">

Ajetaan komennot:

>$ chmod +x shell.sh

>$ ./shell.sh

<img width="351" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/77869c3d-90f8-452a-b72f-9fc96362d641">


## e)

1. Kopioidaan luotu shell.sh tiedosto hakemistoon '**/usr/local/bin**

>$ sudo cp shell.sh /usr/local/bin/shell

2. Annetaan komennolla suoritusoikeudet

>$ sudo chmod +x /usr/local/bin/shell'

3. Testataan, että komento toimii ilman polun kirjoittamista.

>$ shell

<img width="359" alt="image" src="https://github.com/AlexKiippa/LinuxPalvelimetKurssi/assets/98153476/c5f6ee71-dd91-4e0a-bae2-65950a9d2cfe">



## f) 
Tehtävää en ihan ehdi ennen deadlineä joka on 24 tuntia ennen seuraavan tunnin alkamista joten täydennän tämän maanantai illalla.

## g)

Asensin debian 12-Bookworm -järjestelmän uudelle tyhjälle virtuaalikoneelle. Asensin ja otin käyttöön palomuurin. Ja katsoin, että koneella on toimiva nettiyhteys.
Tämän tekeminen onnistui kurssin ensinmäisen viikon dokumentaation ansiosta todella hyvin ja helposti.

