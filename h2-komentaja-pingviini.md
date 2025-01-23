# Perusteet komentorivin käytöstä
Komentokehoite kirjoitetaan promptin jälkeen. Seuraavaksi esittelen muutamia tavallisimpia komentokehoitteita.
-	pwd näyttää working directoryn..
-	ls listaa tiedostot ja kansiot working directory sisällä
-	cd kissakansio/ komennolla siirrytään working directoryssa olevan kansion sisälle, joka on tässä tapauksessa kissakansio.
-	cd .. komento peruuttaa yhden askeleen taaksepäin takaisin edelliseen sijaintiin.
-	mkdir koirakansio komennolla saadaan luotua uusi kansio, sen kansion tai hakemiston sisään, missä me sillä hetkellä olemme. Tässä tilanteessa luotiin kansio nimeltä koirakansio.
-	sudo apt-get update päivittää saatavilla olevat paketit. sudo komennon edessä tarkoittaa komennon suorittamista pääkäyttäjänä.
-	sudo apt-get install komennolla voidaan asentaa monia erilaisia sovelluksia koneelle lisäämällä installin perään asennettavan ohjelman nimen, kuten micro. 
Peruskomentoja on luonnollisesti paljon enemmän, mutta tässä oli vain muutama esimerkki.
Jonkin verran komentorivin käyttöä harjoiteltuani, huomaan miten nopea ja kätevä tapa se on käsitellä tiedostoja. 
Lähde: Tero Karvinen.Command Line Basics Revisited. https://terokarvinen.com/2020/command-line-basics-revisited/?fromSearch=command%20line%20basics%20revisited

# h2 Raportti


**23.1.2025 9:00**


Tehtävänantona oli asentaa Linuxille micro-editori. Se tuli asennettua jo viikon luennolla tehtävien harjoitusten lomassa, mutta se onnistuu komentorivillä komennolla: sudo apt-get install micro.

![image](https://github.com/user-attachments/assets/9a285695-9068-4d48-81a1-5ca7857bc24c)


![image](https://github.com/user-attachments/assets/67afcc8f-0880-430a-b9a1-ad6c821d995c)


 

Muistaa tallentaa tekstin ctrl + s ja tekstieditorista pääsee poistumaan ctrl + q


 ![image](https://github.com/user-attachments/assets/dc23bc8c-d79d-408b-9916-0d977d700e4d)

 ![image](https://github.com/user-attachments/assets/09a6c140-e9fa-4b4e-af3f-801496168c50)



 
Tehtävässä annettiin ohjeeksi asentaa kolme vapaavalintaista terminaaliohjelmaa, ja aloitinkin opettajan näyttämistä yksinkertaisista ja hauskoista ohjelmista.


![image](https://github.com/user-attachments/assets/2ec8992d-a860-4f27-ab0b-32c4ef62247b)


![image](https://github.com/user-attachments/assets/2bb8538a-d5d9-47df-87be-5a99117bdc6b)


 
 
Monen ohjelman lataaminen onnistuu, kun laittaa ohjelman nimet peräkkäin (välilyönneillä eroteltuna) sudo apt-get install koemnnon perään.

![image](https://github.com/user-attachments/assets/cfd3ef19-ab83-4f77-83ce-390e72591501)

 
Tässä siis ladataan kaksi ohjelmaa, alapuolella näkyvä sl(juna) sekä alempana oleva tldr(komentokehoiteapuri) ohjelma. Kerralla voidaan asentaa myös enemmän kuin kaksi ohjelmaa, listaamalla ne esimerkin tavoin peräkkäin.

![image](https://github.com/user-attachments/assets/03099cce-8cd4-4c7d-8d07-418af046d681)

 
sl on ”hauska” ohjelma, joka ajaa junan ruudun läpi.
tldr on ohjelma, jonka auttaa komentorivityökalujen käytössä antamalla selkeitä ohjeita ja esimerkkejä. Idean sovellukseen löysin googlaamalla ’terminal programs linux’ ja hakutuloksista löysin tämän: https://www.reddit.com/r/linux/comments/1ajslo3/what_are_your_most_valuable_and_loved_command/
Sovelluksen asennusohjeen löysin täältä https://www.youtube.com/watch?v=k2CMtmfWfyQ


Tässä esimerkki find komennon käytöstä:

![image](https://github.com/user-attachments/assets/019bc4a3-db98-445e-b534-e2c3af01301b)

 
Esimerkki grep komennon käytöstä:

![image](https://github.com/user-attachments/assets/5158b61e-34ec-41a9-888e-d798ac08a934)

 





Tämä kansio on hakemistopuun ylimpänä, jossa on ylimmältä tasolta katsottavissa mitä kansioita kone sisältää.

![image](https://github.com/user-attachments/assets/5c8e3e08-96f4-4760-87c9-851fbddcacee)

 
Seuraavassa kuvassa näytetään kaikkien käyttäjien /home/ hakemistot, ja tässä tapauksessa niitä on vain yksi -> maaria

![image](https://github.com/user-attachments/assets/18e1ba7c-4c3f-49d2-8742-f02f5d1b829f)

 
Seuraavaksi näimme käyttäjän maaria kansiot, jonne hän kaikki omat henkilökohtaiset tiedostonsa voi tallentaa. Vaihtoehtoja on useita erilaisia kansioita tarpeen mukaan. Kansioita voi myös halutessaan luoda lisää.

![image](https://github.com/user-attachments/assets/4aa11c76-4b3e-4699-ae67-f1c86e1cbb7e)

 
cd .. komennolla peräännyin hakemistosta, jossa sillä hetkellä olin. Siirryin etc hakemistoon. etc hakemisto sisältää systeemin ja konfigurointiin liittyvät tiedostot.

![image](https://github.com/user-attachments/assets/512a0429-cf78-4e22-a1d5-f78b292c1145)

 
Media kansio hakemistojuuressa voisi sisältää esimerkiksi usb:ltä tuotuja tietoja, mutta tässä hetkessä oma mediakansioni oli tyhjä, koska ls komennolla ei tullut mitään kansioita tai tiedostoja näkyville.

![image](https://github.com/user-attachments/assets/3ccdb11b-ee88-4c47-b6e5-409dea131f6f)

 
log kansio sisältää erilaisia järjestelmätason lokitiedostoja, jotka taas sisältävät tietoa järjestelmän toiminnasta ja tapahtumista. Tämän kansion tietoja voidaan käyttää ongelmien selvittämiseen, diagnosointiin ja järjestelmän ylläpitoon.

![image](https://github.com/user-attachments/assets/58c4d1f1-413c-4475-82c7-6674673ed3b9)

 
Lähdin tutustumaan apt kansioon ja sen sisällä olevaan history.log tiedostoon.

![image](https://github.com/user-attachments/assets/63a8aefa-7b07-46b6-a213-2de196b88970)


![image](https://github.com/user-attachments/assets/2c6cc143-f817-4258-a3d5-265f9cfd43be)


 
 
history.log tiedosto näyttää tapahtuneet pakettitoiminnot, ja nämä tiedot voivat auttaa vianmäärityksessä, tiedon history.log tiedostosta löysin täältä: https://askubuntu.com/questions/1410780/what-is-the-difference-relation-between-var-log-apt-history-log-and-var-log-ap



# grep harjoituksia


grep komennolla voin asettaa haettavaksi rivejä tietyllä sanalla. Laitoin hakusanaksi punainen, ja grep komennolla näytettiin tekstitiedostosta kaikki rivit, joilla sana punainen esiintyy.

![image](https://github.com/user-attachments/assets/286b6212-1c67-4b7f-87b8-f9601a0f77fd)

 
grep komennolla voidaan myös suodattaa pois näytettäviä rivejä, kuten tässä tapauksessa suodatin pois kaikki rivit missä lukee punainen, joten näytettiin vain ne rivit joissa ei lue sanaa punainen.

![image](https://github.com/user-attachments/assets/5b6645a7-2a48-49c4-9862-a92c3ac6887f)

 
Alemmassa esimerkissä olen suodattanut pois kaikki rivit, joissa lukee sana punainen ja lisäksi -v toiminnolla tulee listatuksi rivinumerot joilla teksti tiedostossa esiintyy.

![image](https://github.com/user-attachments/assets/ae826a35-75d6-43a8-86b0-dbb50cfb4eb3)

 
Alla olevan komennon lopussa oleva * tarkoittaa että haetaan kaikki hakemistot ja tiedostot, joiden nimessä esiintyy sana kissa.

![image](https://github.com/user-attachments/assets/8e57e30c-3d0b-4401-9ea1-b37f9512b329)

 
grep apuja sain tältä videolta https://www.youtube.com/watch?v=Tc_jntovCM0

# pipes


Näyttää ma kansiosta ne vain ne tiedostot, joissa lukee kissa

![image](https://github.com/user-attachments/assets/1cd414e4-a94b-4ce8-9bbd-7d5b32722b8f)

 
Listaa journlista 10 tapahtumaa, ja lisää niihin rivinumerot.

![image](https://github.com/user-attachments/assets/9b6573bb-6fc9-4c70-8873-6fd2e8f2e10a)

Tämä esimerkki näytettiin Tero Karvisen Linux-luennolla 21.1.2025 17:40-23:30 ja halusin päästä kokeilemaan sitä myös itse käytännössä.
 

Seuraavaksi siirryin listaamaan koneen rautaa, ja koska minulla ei näemmä ollut asennettuna lshw niin asensin sen ensin.


![image](https://github.com/user-attachments/assets/9b35e89f-4ca3-4caf-ad38-a85f95f19343)

 
Seuraavaksi pääsin tarkastelemaan virtuaalikoneen ominaisuuksia tarkemmin.

![image](https://github.com/user-attachments/assets/2aa19739-0b73-40b2-ba03-cf020314ea8b)

 

**system	VirtualBox**
	Virtuaalikoneen malli
**memory	128KiB BIOS**
	Tämä muistialue on varattu BIOSille, eli koneen käynnistyessä tarvittaville prosesseille
**memory	4GiB System memory**
	kertoo järjestelmämuistin koon
**processor	11th Gen Intel(R) Core(TM) i5-1135G7 @ 2.40GHz**
kuvaa koneen prosessoria, joka on sama kuin fyysisen harwaren prosessori, josta virtuaalikone ”lainaa” kapasiteettia

# Lokit
Näissä parissa lokitiedoissa näkyy edeltävän tehtävän lokitiedot.
Ensin olen asentanut lshw jonka jälkeen rivillä näkee sudo ”session”, jonka aikana asennus tapahtuu.
Neljännellä rivillä käytin lshw komentoa, joka näyttää virtuaalikoneen ”hardwaren” ominaisuudet.

![image](https://github.com/user-attachments/assets/7834b191-ba2a-4023-a0fd-0e4aa5c7ca09)


**23.1.2025 13:11**
Sain tehtävän tehtyä, ja siihen kuluikin yllättävän paljon aikaa. Komentokehoitteen käyttö oli hauskaa, ja huomaan että siinä kehittyy koko ajan mitä enemmän sitä käyttää. Uusia komentoja oppii koko ajan ja niitähän on varmasti lähes loputtomasti.


 
Tehtävän lähde: Tero Karvinen. h2 Komentaja Pingviini. https://terokarvinen.com/linux-palvelimet/. Luettu: 23.1.2025
