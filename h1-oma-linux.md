# Raportin kirjoittaminen
-Raportin on tärkeää olla täsmällinen ja sitä kirjoitetaan koko ajan samalla kun tehtävää tehdään.
-Raportti helpottaa ongelmanratkaisussa, kun tilannetta on jäsennelty, ja pysyy selvillä mitä on jo yritetty.
- Toistettava toisen henkilön toimesta. Kuka vaan raporttia lukiessa pystyy tekemään samat asiat ja pääsee samaan lopputulokseen.
- Täsmälliset komennot ja sivut millä vieraillut. Kellonajat kuvaavat työvaiheisiin kulunutta aikaa. Onnistumiset ja ongelmat kuvattava tarkasti, jotta myös toinen henkilö pystyy asian raportin pohjalta toteuttamaan.
-Helppolukuisuutta lisätään väliotsikoilla ja selkeällä kielellä. 
-Lähteisiin viitattaessa ne on selkeästi merkittävä tekstiin, ettei tule vaaraa plagioinnista.
- Pahoja mokia on vältettävä. Asian täytyy pysyä totuudessa, plagiointi on ehdottoman kiellettyä, koskee sekä tekstiä, että kuvia.
Lähde: Tero Karvinen. 4.7.2006. Raportin kirjoittaminen. https://terokarvinen.com/2006/raportin-kirjoittaminen-4/. Luettu 15.1.2025

# Free Software Foundation
-	Vapaalla ohjelmistolla tarkoitetaan ohjelmaa, joka on käyttäjän vapaasti ajettavissa, kopioitavissa, muokattavissa ja paranneltavissa.
-	Vapaa ohjelmisto ei kuitenkaan aina ole ilmainen rahallisesti, vaan sillä tarkoitetaan enemmän käytön suomaa vapautta.
-	Niin sanotut ’nonfree’- ohjelmat ovat käyttäjien kontrollin yläpuolella: Ohjelma siis kontrolloi käyttäjää ja ohjelmiston kehittäjät kontrolloivat ohjelmaa.
-	Avoin lähdekoodi on yleensä ilmainen sekä käyttäjien vapaasti muokattavissa ja paranneltavissa.
## Neljä vapautta
_Freedom 0_
Vapaus ajaa ohjelmaa kuten käyttäjä haluaa mihin tarkoituksiin tahansa. Se ei vaadi yhteydenpitoa kehittäjän tai kenenkään tietyn toimijan kanssa. Käyttäjä on siis täysin vapaa käyttämään ohjelmaa omalla tavallaan ja jakamaan sitä myös muille, jotka voivat sitä vapaasti hyödyntää. Vaikka koodi on vapaasti käytettävissä ja jaettavissa, se ei takaa sen toimivuutta ja käyttökelpoisuutta kaikissa ympäristöissä.

_Freedom 1_
Vapaus opiskella ohjelman toimintaa ja muokata sitä omiin tarpeisiin sopivaksi. Tämä edellyttää pääsyä oikeaan lähdekoodiin. Lähdekoodi on siinä muodossa, että siihen pystyy tekemään muokkauksia. Muokatusta lähdekoodista tulee muokkauksien myötä kehittäjän oma versio koodista. Vapaus mahdollistaa muokatun koodin käyttämistä alkuperäisen tilalla. Tätä vapautta voidaan myös yrittää estää muiden käyttäjien toimesta, toimittamalla ohjelma tuotteessa, joka on suunniteltu ajamaan muiden käyttäjien versioita ja näin estämällä toisen käyttäjän tekemän version toimimisen.

_Freedom 2_
Vapaus jakaa kopioita ohjelmasta, joilla voi olla avuksi muille. Tämän voi tehdä ilmaiseksi tai pyytää rahaa kopioista, ilman minkään tahon suostumusta. Vapaa pääsy lähdekoodiin on oltava mahdollinen. Tämän vapauden myötä ohjelmaa voi muokata juuri niin kuin haluaa omiin tarpeisiin, eikä koodin käytöstä tai muokkaamisesta tarvitse informoida mitään tahoa.

_Freedom 3_ 
Vapaus jakaa käyttäjän muokkaamia kopioita ohjelmasta muille. Nämä muutokset voivat hyödyttää koko yhteisöä. Oman muokkaamaan version ohjelmasta voi julkaista vapaana ohjelmana. Ohjelman vapaan jakelun täytyy pitää sisällään esimerkiksi suoritettavat tiedostot kuten lähdekoodin. 

Vapaa ohjelma tarjoaa mahdollisuuden hyödyntää näitä vapauksia. Jos käyttäjän oikeudet muokata ohjelmaa ovat rajoitetut, silloin ei voida puhua vapaasta ohjelmasta. Tiettyjä sääntöjä voidaan kuitenkin sisällyttää vapaiden ohjelmistojen kanssa toimimiseen. Ohjelmien muokkaamisessa ei voi asettaa rajoituksia muille käyttäjille ohjelman muokkaamiseen. 
## Lakiin liittyvät näkökulmat
-	Jotta vapaus ohjelmistojen kehityksessä säilyy, niiden on oltava pysyviä niin kauan kun mitään väärää ei niiden avulla tehdä. Jos ohjelmiston kehittäjä 	lisää rajoituksia omaehtoisesti ohjelmiston ehtoihin, ei se enää ole vapaasti hyödynnettävissä.
## Sopimukseen perustuvat lisenssit
-	Suurin osa vapaat ohjelmistolisenssit perustuvat tekijänoikeuteen. Se on rajoitettua, millaisia vaatimuksia tekijänoikeudella voidaan asettaa. 
## Lähde:
GNU Operating System. What is Free Software? https://www.gnu.org/philosophy/free-sw.html. Luettu: 15.1.2025.

# h1 Raportti
Tehtävänantona oli tehdä uusi virtuaalikone, johon asennetaan Linux. Tästä kirjoitetaan myös huolellinen raportti eri työvaiheista. Lähdin lähestymään tehtävään selvittämällä oman tietokoneeni ominaisuuksia ja soveltuvuutta kyseisen tehtävän suorittamiseen.

Minulla oli käytössä kannettava tietokone:
•	Lenovo Ideapad 3
•	Suoritin: 11th Gen Intel® Core
•	RAM: 8,00 Gt, josta käytettävissä 7,80Gt.
•	C: tallenustila 475Gt, käytettävissä 324Gt
•	Käyttöjärjestelmä: Windows 11 versio 24H2

16.1.2025 14:00
Aloitin tutustumalla virtuaalikoneen asennusohjeisiin (https://terokarvinen.com/2021/install-debian-on-virtualbox/). Sivulta löysin suoran linkin virtuaalikoneen asentamiseen sekä Debian ISO Imagen latausohjeet.
Aloitin lataamalla Debian ISO Imagen ja hain . https://cdimage.debian.org/debian-cd/current-live/amd64/iso-hybrid/ verkkosivuilta uusimman version joka oli nimellä: 
debian-live-12.9.0—amd64-xfce.iso
Sen jälkeen siirryin virtuaalikoneen lataamisen pariin. Suora linkki virtuaalikoneen lataamisen löytyi Tero Karvisen ohjeista (Install Debian on Virtualbox - Updated 2024) ja valitsin siellä windowsille sopivan virtuaalikoneen.
![image](https://github.com/user-attachments/assets/09a07dca-fc06-4f79-af9c-13ca2667b617)

