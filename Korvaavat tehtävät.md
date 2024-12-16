Tehtävänäni oli testata 3 kurssilaisen omat moduulit ja raportoida kokeilut. 

## Ensimmäinen testattu moduuli.
Ensimmäinen moduuli jonka testasin löytyi täältä: 
https://github.com/Pakknoo/Palvelinten-hallinta/blob/main/H4.md
https://github.com/Pakknoo/Palvelinten-hallinta/blob/main/H5.md 

Oman moduulini jäljiltä, minulla oli jo luotuna master ja minion koneet. 
Varmistin vielä, että pingi toimii.

![master testping](https://github.com/JohannaLap/H8/blob/main/master%20testping.png)

Muistelin jo aiemmin asentaneeni unattended-upgrades -paketin, mutta kokeilin sen asennuksen kuitenkin. 
Ja kuten näemme, paketti oli jo asennettuna.

Varmistin vielä systemctl status komennolla, että tila näkyy aktiivisena. 

![asennuksen tarkistus](https://github.com/JohannaLap/H8/blob/main/asennuksen%20tarkistus.png)

Etenin ohjeiden mukaisesti. En suoraa löytänyt 'sudoedit /etc/apt.conf.d/50unattenden-upgrades' komennolla haluttua tiedostoa. 
Jouduin sitä hieman etsiskelemään. 
![etsimis komento 50unattended](https://github.com/JohannaLap/H8/blob/main/etsimis%20komento%2050unattended.png)

Löysin oikean polun. 

![oikeapolku](https://github.com/JohannaLap/H8/blob/main/oikeapolku.png)

![haluttunäkymä](https://github.com/JohannaLap/H8/blob/main/haluttun%C3%A4kym%C3%A4.png)

Raporttia seuratessani, eteneeminen meni niin että tiedostoon lisättiin kohtia. Halusin tehdä kokeen, että jos settaa
automatic-rebootiin arvon false, tapahtuuko mitään. Eli toimin nyt päinvastoin mitä raportissa alunperin oli kokeiltu. 

![reboot](https://github.com/JohannaLap/H8/blob/main/reeboot.png)

Varmistin vielä raportissakin varmistetun tiedoston 20auto-upgrades ja hyvältä näytti. 

![20auto-upgrades](https://github.com/JohannaLap/H8/blob/main/20auto-upgrades.png)

Otin automaattiset päivitykset käyttöön masterilla. 

![aut.päivitykset masterilla](https://github.com/JohannaLap/H8/blob/main/aut.p%C3%A4ivitykset%20masterilla.png)

![ilmoitus](https://github.com/JohannaLap/H8/blob/main/ilmoitus.png)

Raportin mukaisesti jatkoin luomalla kansion masterille.

![mkdir master](https://github.com/JohannaLap/H8/blob/main/mkdir%20master.png)

Kopioin tiedostot /srv/salt/updates kansioon. 

![tiedostojenkopiointi](https://github.com/JohannaLap/H8/blob/main/tiedostojenkopiointi.png)

Loin init.sls tiedoston. 

Lisäsin tiedostoon sisällön. Jätin susosiolla cmd.run pois, koska sitä ei raportissa oltu saatu toimimaan. 
Jos aikaa olisi ollut enemmän, tai testattavia moduuleja vähemmän, olisi tuota voinut ajan kanssa selvitellä ja testailla. 

![initsls](https://github.com/JohannaLap/H8/blob/main/initsls.png)

Ja lopputulos oli toivotun lainen. 

![lopputulos](https://github.com/JohannaLap/H8/blob/main/lopputulos.png)

## Toinen testattu moduuli

Toinen testattu moduuli löytyy täältä:

https://github.com/guikka4/Module_project/blob/main/Module_project.md

Tässä oli tarkoituksena luoda kolme virtuaalikonetta, master ja minionit. Tarkoituksena käyttää Virtualboxia ja vagranttia. Näiden käyttö toki tuttua jo kurssin tiimoilta ja omasta moduulistanikin.

Loin ensiksi uuden kansion testaamista varten, jonka jälkeen siirryin kansion sisälle. 

![moduulitestiluonti](https://github.com/JohannaLap/H8/blob/main/moduulitestiluonti.png)

![cd mosuulitesti](https://github.com/JohannaLap/H8/blob/main/cd%20mosuulitesti.png)

Latasin imagen. Latauksen jälkeen varmistin, että Vgarantfile näkyy.

![Debian bookworm imagelataus](https://github.com/JohannaLap/H8/blob/main/Debian%20bookworm%20imagelataus.png)

Muokkasin vagrantfilen sisältöä. Poiketen seuraamastani moduuliraportista, muutin koneiden nimiä ja ip osoitteita. 

![vagrantfile](https://github.com/JohannaLap/H8/blob/main/vagrantfile.png)

Käynistin vagrantin avulla virtuaalikoneet. Varmistin, että koneet ilmestyvät virtualboxiin näkyviin. 

![vagrantup]()

![vbox](https://github.com/JohannaLap/H8/blob/main/vagrantup.png)

Testasin yhteydet minioneilta masterille ja, että salt on aktiivisena. 

![minion1](https://github.com/JohannaLap/H8/blob/main/minon1.png)

![minion2](https://github.com/JohannaLap/H8/blob/main/minion2.png)

Masterin tila oli inactivena, joten käynnistin sen. 

![mastertilamuutetti](https://github.com/JohannaLap/H8/blob/main/mastertilamuutetti.png)

Tarkistin avaimet ja hyväksyin ne. 

![masteravaimet](https://github.com/JohannaLap/H8/blob/main/masteravaimet.png)

Tämän jälkeen testasin masterilta test pingin. 

![testping](https://github.com/JohannaLap/H8/blob/main/testping.png)

Seuraavaksi oli tarkoitus asentaa apache2 masterille.

![apachemasterille](https://github.com/JohannaLap/H8/blob/main/apachemasterille.png)

Muutin aloitus sivua. 

![aloitussivunmuutto](https://github.com/JohannaLap/H8/blob/main/aloitussivunmuutto.png)

![curltesti](https://github.com/JohannaLap/H8/blob/main/curltesti.png)

Sitten tein apachelle configuraatio tiedostoon sisällön. Sisältö on muutoin sama kuin seuraamassani raportissa, 
mutta servername ja serveralias nimet muutin omikseni.

![apachemuokkaaminen](https://github.com/JohannaLap/H8/blob/main/apachemuokkaaminen.png)

Tämän jälkeen muokkasin sivua.

![testaillaan](https://github.com/JohannaLap/H8/blob/main/testaillaan.png)

Aktivoin apachen uuden configuraation ja poistin vanhan käytöstä. Testasin curlilla. Saamani tulos curlilla, 
oli aivan eri pitä moduulin raportissa. 

![apachemuutettu](https://github.com/JohannaLap/H8/blob/main/apachemuutettu.png)

Seuraavaksi oli tarkoitus saltin kautta asentaa apache minioneille. 
Homma lähti tuttuun tapaan liikkeelle polun ja tiedoston luomisella. 

![initslsapache](https://github.com/JohannaLap/H8/blob/main/initslsapache.png)

Sitten testasin. Koska jätin tuon apacheuserin lisäämisen tekemättä, tulos näytti kutakuinkin samalta kuin raportissa. 
Poislukien tuo, ettei käyttäjästä toki ollut mainintaa.

![stateapplytesti](https://github.com/JohannaLap/H8/blob/main/stateapplytesti.png)

Tein muokkaukset sls tiedostoon, ennen kuin lähdin ajamaan minioneille.

![apachesls](https://github.com/JohannaLap/H8/blob/main/apachesls.png)

Sitten testasin ajaa sls teidoston minion1. Ja tulos oli toivotun lainen. 

![minion1](https://github.com/JohannaLap/H8/blob/main/minion1.png)

Seuraavaksi muokkasin minionilla suoraan sivun confaustiedostoa.

![conftiedostonmuokkaus](https://github.com/JohannaLap/H8/blob/main/conftiedostonmuokkaus.png)

Sitten toistettiin, jo aiemmassa vaiheessa tutuksi tulleet vaiheet uuden configuraatiotiedoston aktivoimisesta.

![sivunvoimaantulo](https://github.com/JohannaLap/H8/blob/main/sivunvoimaantulo.png)

Testasin curlilla että näkymä oli halutunlainen. testasin näkymän myös selaimessa.

![minioncurl](https://github.com/JohannaLap/H8/blob/main/minioncurl.png)

![apacheweb](https://github.com/JohannaLap/H8/blob/main/apacheweb.png)

Raportin seuraavassa vaiheessa oli tarkoitus asentaaa PostgreSQL minion2. Jälleen aluksi tehdään manuaalisesti, 
ennen kuin lähdetään automatisoimaan. 

![potgre](https://github.com/JohannaLap/H8/blob/main/potgre.png)

![tarkistus](https://github.com/JohannaLap/H8/blob/main/tarkistuspsql.png)
Loin tietokannalle nimen ja käyttäjän.

![psql tietokanta ja käyttäjä luonti](https://github.com/JohannaLap/H8/blob/main/psql%20tietokanta%20ja%20k%C3%A4ytt%C3%A4j%C3%A4%20luonti.png)

Sitten loin taulun. Taulussa määriteltynä automaattisesti kasvava numero sekä merkkijonon maksimipituus (15). 
Lisäsin tauluun raportin mukaiset teidot ja tarkistin, että taulukko näytti toivotulta.

![taulu ja sisältö](https://github.com/JohannaLap/H8/blob/main/taulu%20ja%20sis%C3%A4lt%C3%B6.png)


Sitten siirryttiin salttiin. Siirryin masteri koneelle takaisin. Loin kansion postgresql varten. Siirryin muokkamaan
sls tiedsotoa.

![mastersql](https://github.com/JohannaLap/H8/blob/main/mastersql.png)

Lisäsin sisällön sls tiedostoon masterille. 

![sqlsls](https://github.com/JohannaLap/H8/blob/main/sqlsls.png)

Kokeilin state.applyn vielä. 

![lopputulos](https://github.com/JohannaLap/H8/blob/main/lopputulos.png)


