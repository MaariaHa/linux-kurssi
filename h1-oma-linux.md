Tässä tehtävässä olen tiivistänyt kaksi artikkelia, sekä kuvannut raportissa virtuaalikoneen tekemistä sekä Linuxin asennusta. 

# Raportin kirjoittaminen
-Raportin on tärkeää olla täsmällinen ja sitä kirjoitetaan koko ajan samalla kun tehtävää tehdään.
-Raportti helpottaa ongelmanratkaisussa, kun tilannetta on jäsennelty, ja pysyy selvillä mitä on jo yritetty.
- Toistettava toisen henkilön toimesta. Kuka vaan raporttia lukiessa pystyy tekemään samat asiat ja pääsee samaan lopputulokseen.
- Täsmälliset komennot ja sivut millä vieraillut. Kellonajat kuvaavat työvaiheisiin kulunutta aikaa. Onnistumiset ja ongelmat kuvattava tarkasti, jotta myös toinen henkilö pystyy asian raportin pohjalta toteuttamaan.
-Helppolukuisuutta lisätään väliotsikoilla ja selkeällä kielellä. 
-Lähteisiin viitattaessa ne on selkeästi merkittävä tekstiin, ettei tule vaaraa plagioinnista.
- Pahoja mokia on vältettävä. Asian täytyy pysyä totuudessa, plagiointi on ehdottoman kiellettyä, koskee sekä tekstiä, että kuvia.

# Free Software Foundation
-	Vapaalla ohjelmistolla tarkoitetaan ohjelmaa, joka on käyttäjän vapaasti ajettavissa, kopioitavissa, muokattavissa ja paranneltavissa.
-	Vapaa ohjelmisto ei kuitenkaan aina ole ilmainen rahallisesti, vaan sillä tarkoitetaan enemmän käytön suomaa vapautta.
-	Niin sanotut ’nonfree’- ohjelmat ovat käyttäjien kontrollin yläpuolella: Ohjelma siis kontrolloi käyttäjää ja ohjelmiston kehittäjät kontrolloivat ohjelmaa.
-	Avoin lähdekoodi on yleensä ilmainen sekä käyttäjien vapaasti muokattavissa ja paranneltavissa.

## Neljä vapautta
**Freedom 0**
Vapaus ajaa ohjelmaa kuten käyttäjä haluaa mihin tarkoituksiin tahansa. Se ei vaadi yhteydenpitoa kehittäjän tai kenenkään tietyn toimijan kanssa. Käyttäjä on siis täysin vapaa käyttämään ohjelmaa omalla tavallaan ja jakamaan sitä myös muille, jotka voivat sitä vapaasti hyödyntää. Vaikka koodi on vapaasti käytettävissä ja jaettavissa, se ei takaa sen toimivuutta ja käyttökelpoisuutta kaikissa ympäristöissä.

**Freedom 1**
Vapaus opiskella ohjelman toimintaa ja muokata sitä omiin tarpeisiin sopivaksi. Tämä edellyttää pääsyä oikeaan lähdekoodiin. Lähdekoodi on siinä muodossa, että siihen pystyy tekemään muokkauksia. Muokatusta lähdekoodista tulee muokkauksien myötä kehittäjän oma versio koodista. Vapaus mahdollistaa muokatun koodin käyttämistä alkuperäisen tilalla. Tätä vapautta voidaan myös yrittää estää muiden käyttäjien toimesta, toimittamalla ohjelma tuotteessa, joka on suunniteltu ajamaan muiden käyttäjien versioita ja näin estämällä toisen käyttäjän tekemän version toimimisen.

**Freedom 2**
Vapaus jakaa kopioita ohjelmasta, joilla voi olla avuksi muille. Tämän voi tehdä ilmaiseksi tai pyytää rahaa kopioista, ilman minkään tahon suostumusta. Vapaa pääsy lähdekoodiin on oltava mahdollinen. Tämän vapauden myötä ohjelmaa voi muokata juuri niin kuin haluaa omiin tarpeisiin, eikä koodin käytöstä tai muokkaamisesta tarvitse informoida mitään tahoa.

**Freedom 3** 
Vapaus jakaa käyttäjän muokkaamia kopioita ohjelmasta muille. Nämä muutokset voivat hyödyttää koko yhteisöä. Oman muokkaamaan version ohjelmasta voi julkaista vapaana ohjelmana. Ohjelman vapaan jakelun täytyy pitää sisällään esimerkiksi suoritettavat tiedostot kuten lähdekoodin. 

Vapaa ohjelma tarjoaa mahdollisuuden hyödyntää näitä vapauksia. Jos käyttäjän oikeudet muokata ohjelmaa ovat rajoitetut, silloin ei voida puhua vapaasta ohjelmasta. Tiettyjä sääntöjä voidaan kuitenkin sisällyttää vapaiden ohjelmistojen kanssa toimimiseen. Ohjelmien muokkaamisessa ei voi asettaa rajoituksia muille käyttäjille ohjelman muokkaamiseen. 

## Lakiin liittyvät näkökulmat
-	Jotta vapaus ohjelmistojen kehityksessä säilyy, niiden on oltava pysyviä niin kauan kun mitään väärää ei niiden avulla tehdä. Jos ohjelmiston kehittäjä 	lisää rajoituksia omaehtoisesti ohjelmiston ehtoihin, ei se enää ole vapaasti hyödynnettävissä.
-	
## Sopimukseen perustuvat lisenssit
-	Suurin osa vapaat ohjelmistolisenssit perustuvat tekijänoikeuteen. Se on rajoitettua, millaisia vaatimuksia tekijänoikeudella voidaan asettaa. 

# h1 Raportti
Tehtävänantona oli tehdä uusi virtuaalikone, johon asennetaan Linux. Tästä kirjoitetaan myös huolellinen raportti eri työvaiheista. Lähdin lähestymään tehtävään selvittämällä oman tietokoneeni ominaisuuksia ja soveltuvuutta kyseisen tehtävän suorittamiseen.

Minulla oli käytössä kannettava tietokone 💻:

•	Lenovo Ideapad 3

•	Suoritin: 11th Gen Intel® Core

•	RAM: 8,00 Gt, josta käytettävissä 7,80Gt.

•	C: tallenustila 475Gt, käytettävissä 324Gt

•	Käyttöjärjestelmä: Windows 11 versio 24H2

**16.1.2025 14:00**
Aloitin tutustumalla virtuaalikoneen asennusohjeisiin (https://terokarvinen.com/2021/install-debian-on-virtualbox/). Sivulta löysin suoran linkin virtuaalikoneen asentamiseen sekä Debian ISO Imagen latausohjeet.
Aloitin lataamalla Debian ISO Imagen ja hain Debianin https://cdimage.debian.org/debian-cd/current-live/amd64/iso-hybrid/ verkkosivuilta uusimman version joka oli nimellä: 
debian-live-12.9.0—amd64-xfce.iso
Sen jälkeen siirryin virtuaalikoneen lataamisen pariin. Suora linkki virtuaalikoneen lataamisen löytyi Tero Karvisen ohjeista (Install Debian on Virtualbox - Updated 2024) ja valitsin siellä windowsille sopivan virtuaalikoneen.

![image](https://github.com/user-attachments/assets/09a07dca-fc06-4f79-af9c-13ca2667b617)

Lähdin suorittamaan VirtualBoxin asennusohjelmaa.

![image](https://github.com/user-attachments/assets/0d1e9a3b-04c5-4a42-b772-761c55c84fd5)

![image](https://github.com/user-attachments/assets/786c1ed2-a5e8-479f-98be-cffe919a64f7)

Ennen asennuksen käynnistämistä, ikkunassa mainittiin Python Core Packagen asennuksesta, ja varmistin Virtualboxin forumilta, että tähän asennukseen en sitä tarvitse.

![image](https://github.com/user-attachments/assets/5c2c9f91-221f-4f39-9970-1ded6ddc40fa)

Hyväksyin kaikki oletuksena tehdyt valinnat ja jatkoin asennusta.

![image](https://github.com/user-attachments/assets/6f8ee9c2-5a00-4edc-a780-097762219557)

![image](https://github.com/user-attachments/assets/2fe2baf8-b958-4918-b6b6-0d7ea24d7050)

![image](https://github.com/user-attachments/assets/77a320db-ba8c-421b-b531-91ab9896798c)

Latauksen valmistuttua avautui seuraava ikkuna.

![image](https://github.com/user-attachments/assets/6c81dc3e-95e1-4725-b6fa-3269183da0d2)

Valitsen oikeasta reunasta expert mode Tero Karvisen ohjeen mukaan.
Nimesin virtuaalikoneen, ja valitsin tiedostoistani äsken lataamani Debian ISO Imagen. Tyypiksi valitsin Linuxin ja Debianin 64-bittisen ohjeen mukaan.

![image](https://github.com/user-attachments/assets/6b51a9f6-8760-4985-9d2e-00e4b31bc448)

Tarkistin vielä muut välilehdet asennuksen tässä vaiheessa.

![image](https://github.com/user-attachments/assets/f6dd469b-4924-4f30-8906-4d27e2524bb3)

![image](https://github.com/user-attachments/assets/43b093b3-76b4-4d76-960f-204318650ea0)

Tallennustilaan liittyvät asetukset olivat kunnossa ja kone oli valmis asennettavaksi joten klikkasin finish.

![image](https://github.com/user-attachments/assets/4414ae77-78d0-4d46-9452-cc302a120dee)

Vihdoin Linux käynnistyy! Olen asentanut elämäni ensimmäisen virtuaalikoneen ja saanut Linuxin käyttööni.

![image](https://github.com/user-attachments/assets/9cd92f4e-97d5-4f58-9ced-51a523890b15)

Kävin testaamassa weppi-selaimen, ja se toimii kuten pitää.

![image](https://github.com/user-attachments/assets/a0a7f454-ce0f-47e3-bfee-cbd989b60cfc)

Siirryin asentamaan seuraavaksi Debiania uudessa virtuaalikoneessani.

![image](https://github.com/user-attachments/assets/fbb652f8-c301-41bd-b05f-adcb2a6f6140)

![image](https://github.com/user-attachments/assets/f8c01d7b-4751-41ef-b6a5-fa947938597c)

![image](https://github.com/user-attachments/assets/67ef88e0-6490-4f6e-a639-60edfeeafa1e)

**16.1.2025 16:00** Virtuaalikoneen tekeminen ja Linuxin asennus vei itseltäni noin kaksi tuntia aikaa. Koska asia oli itselle täysin uusi ja vieras niin perehdyin ohjeisiin huolellisesti ja tein kaikki työvaiheet rauhassa ja tarkasti. Koko tehtävä oli todella kiva tehdä ja hienoa päästä tutustumaan Linuxiin käyttöjärjestelmänä.


# Lähteet:
Tero Karvinen. 4.6.2006. Raportin kirjoittaminen. https://terokarvinen.com/2006/raportin-kirjoittaminen-4/. Luettu 16.1.2025

Tero Karvinen. Linux Palvelimet 2025 alkukevät. https://terokarvinen.com/linux-palvelimet/. Luettu 16.1.2025

Debian ISO Image. https://cdimage.debian.org/debian-cd/current-live/amd64/iso-hybrid/. Luettu 16.1.2025

VirtualBox Foorumi. https://forums.virtualbox.org/viewtopic.php?t=108582. Luettu. 16.1.2025

GNU Operating System. What is Free Software? https://www.gnu.org/philosophy/free-sw.html. Luettu: 16.1.2025.

