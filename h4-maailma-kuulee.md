# h4


## Johdanto
Aluksi tiivistin Susanna Lehdon ja Tero Karvisen artikkelit liittyen pilvipalvelimien käyttöön ottoon. Sen jälkeen lähdin hankkimaan omaa pilvipalvelinta, lisäämään sinne oman käyttäjän. Tarkoitus oli saada uusi pilvipalvelin toimintakuntoiseksi, jotta voisi julkaista esimerkiksi verkkosivun nettiin kaikkien nähtäville. Tämä tehtävä epäonnistui siinä mielessä, etten saanut verkkosivua toimimaan. Yritän kollegoiden avulla saada ongelman korjatuksi ja tulen tänne päivittämään mikä oli ongelmana, ja miten se korjattiin.


## Tiivistelmä – Teoriasta käytöntöön pilvipalvelimen avulla/ Susanna Lehto


**a)**


-Pilvipalvelin hankittiin DigitalOceanilta.


-Domain NameCheapilta.


-Molemmat saatiin ilmaiseksi GitHub Student Developer Pack:in kautta.


-Pilvipalvelimen käyttöjärjestelmäksi valittiin Debian 11 x64


-Datakeskukseksi valittiin Amsterdam


**b)** 


-Palvelin suojattiin palomuurilla


-root-käyttäjällä kirjauduttiin palvelimelle


-Palvelin päivitettiin


-Asennettiin palomuuri


-Palomuuriin tehtiin reikä 22/tcp porttia varten


-Palomuuri laitettiin päälle


**c)**


-Tehtiin uusi pääkäyttäjä raportin kirjoittajan omalla nimellä


-root-käyttäjä lukittiin


-Domain nimen pingaamista kokeiltiin, joka jatkoi pingaamista, kunnes komento tapettiin


-Apache weppipalvelin asennettiin


-Palomuuriin tehtiin toinen reikä 80/tcp portille.


-Firefox selaimella Apache testi sivu toimi.


-Micro asennettiin


-Seuraavaksi korvattiin testisivu, muokkaamalla index.html tiedostoa


-Muokattu sivu testattiin vielä selaimessa toimivaksi


**f)**


-Ensin otettiin SSH yhteys palvelimelle.


-Asennettiin pakettien päivitykset sekä tietoturvapäivitykset uudelle virtuaalipalvelimelle


-$ sudo apt-get update


-$ sudo apt-get upgrade


-$ sudo apt-get dist-upgrade


Lähde: https://susannalehto.fi/2022/teoriasta-kaytantoon-pilvipalvelimen-avulla-h4/


## Tiivistelmä  - First Steps on a New Virtual Private Server – an Example on DigitalOcean and Ubuntu 16.04 LTS/ Tero Karvinen


-Konfiguroidaan uusi virtuaalipalvelin DigitalOceanista ja DNS nimi NameCheapista


**-Erittäin tärkeää käyttää aina vain hyviä salasanoja.**


-Uuden virtuaalipalvelimen luominen alkaa kirjautumalla DigitalOceaniin, artikkelissa luodaan Ubuntu 16.04 LTS virtuaalipalvelin.


-Ensimmäistä kertaa otetaan yhteys palvelimelle root-käyttäjänä.


-Tehdään palomuuri ja siihen reikä 22/tcp portille.


-Tehdään sudo käyttäjä nimettynä henkilölle joka palvelinta käyttää


-Suljetaan root-käyttäjä


-Päivitetään ohjelmistot


-Apachen asentamisen jälkeen tehdään palomuurille reikä porttiin 80/tcp


-Julkisen DNS nimen voi tehä NameCheapissa


Lähde: https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/


**a) Vuokraa oma virtuaalipalvelin haluamaltasi palveluntarjoajalta.**	


**5.2.2025 13:20**


Vuokrasin UpCloudista serverin seuraavilla spekseillä:


![image](https://github.com/user-attachments/assets/85734a23-22b5-42a5-8896-fc3f773966c5)


![image](https://github.com/user-attachments/assets/52ce9484-fb7a-405d-9f58-d64e660cc30e)


![image](https://github.com/user-attachments/assets/0f0f957a-9d94-4d84-afeb-c904a04b1405)


Siirryin virtuaalikoneelle seuraavaan vaiheeseen.


Alkuun perinteiset pakettien päivitykset.



![image](https://github.com/user-attachments/assets/f0e9b90b-0a77-4fa9-a52e-1346cb69bda3)


Seuraavaksi asentamaan ssh clienttiä.



![image](https://github.com/user-attachments/assets/6d25d36f-27a5-4d93-b74e-0e5f787ef92f)




Seuraavaksi SSH avainten luominen.



![image](https://github.com/user-attachments/assets/e5a1c21b-e444-44d9-98d3-1227c30e7869)


Kolme kertaa enteriä painamalla pääsin eteenpäin avainten luonnissa, nyt minulla oli sekä julkinen, että yksityinen avain luotuna.





![image](https://github.com/user-attachments/assets/804ec527-4076-4b1d-b8ca-23760a3330b8)




Kävin kopioimassa julkisen avaimen.


![image](https://github.com/user-attachments/assets/5ad6d0f8-eac6-4b49-8eb5-b9141e4bb4c6)



Kävin tallentamassa julkisen avaimen UpCLoudin serverille.



![image](https://github.com/user-attachments/assets/0305e944-4a0f-4e4c-b601-8e43dce943e5)





Sitten olin valmis luomaan serverin ja klikkasin deploy.


![image](https://github.com/user-attachments/assets/3aa70866-141f-49f2-8535-2ced519c019d)



Meni hetken aikaa, että serveri oli luotu. Värikäs pallo vasemmassa yläkulmassa muuttui vihreäksi, kun serveri oli valmis.



![image](https://github.com/user-attachments/assets/b027d4e8-64ef-4ec9-b862-8439c4af3ba4)




Kävin kopioimassa UpCloudista IP-osoitteen ja kirjauduin virtuaalikoneessa root- käyttäjänä serverille. Siirryin seuraavaan tehtävään.



**b)Tee alkutoimet omalla virtuaalipalvelimellasi: tulimuuri päälle, root-tunnus kiinni, ohjelmien päivitys.**	


**5.2.2025 14:00**

Kirjauduin root-käyttäjänä sisään.


![image](https://github.com/user-attachments/assets/64a1f67a-9637-4b6b-acc2-04bfa1d45303)




Loin uuden käyttäjän.


![image](https://github.com/user-attachments/assets/39718154-efbf-42af-9a1c-1dbec8cd4f19)



Ja lisäsin salasanan, sekä käyttäjän nimen.


Lisäsin käyttäjän maaria sudo ryhmään.



![image](https://github.com/user-attachments/assets/439f10b4-3e9d-407f-a3fe-5065816d10af)



Seuraavaksi lähdin kopioimaan SSH asetuksia root-käyttäjältä, tälle uudelle juuri luomalleni käyttäjälle.




![image](https://github.com/user-attachments/assets/a8a4f97e-0bc3-4cdb-92be-7fd713fc5aed)



Muokkasin asetuksia niin, että pystyn kirjautumaan serverille omana käyttäjänä.



![image](https://github.com/user-attachments/assets/50bab128-55b7-472a-80d4-bd1da992e67e)




Testasin vielä sisäänkirjautumisen root-käyttäjänä, ja näytti onnistuvan.



![image](https://github.com/user-attachments/assets/69969575-63b3-445d-851f-1a83dab93827)



Sitten kokeilin kirjautua sisään omalla käyttäjätunnuksella.




![image](https://github.com/user-attachments/assets/a491c15e-39c6-4912-8b2b-d40761e0d928)




Sekin onnistui!


Seuraavaksi kävin laittamassa palomuurit kuntoon.



![image](https://github.com/user-attachments/assets/34aad608-4f06-4bb8-91f1-110e70696564)


![image](https://github.com/user-attachments/assets/0d28908b-67c4-4e93-9d37-ea9e5cb2ab74)


![image](https://github.com/user-attachments/assets/f4012102-986a-435e-88b0-ce783bb03499)



Huomasin, että minulta oli tekemättä sudo apt-get dist-upgrade, joka päivittää ja asentaa uusia paketteja ja poistaa vanhentuneita, joten tein sen tässä välissä. Siinä menikin yllättävän kauan.
Seuraavaksi suljin root-käyttäjän.



![image](https://github.com/user-attachments/assets/80f822a9-d818-452f-9121-f0f3ba86248b)


![image](https://github.com/user-attachments/assets/c08d5d0f-2bb3-4bb4-9754-eefbdf19f641)




**c)Asenna weppipalvelin omalle virtuaalipalvelimellesi. Korvaa testisivu. Kokeile, että se näkyy julkisesti.**	


**5.2.1015 14:35**


Seuraavaksi siirryin asentamaan weppipalvelinta uudelle virtuaalipalvelimelleni.
Kirjauduin ensimmäiseksi sisään palvelimelle.




![image](https://github.com/user-attachments/assets/cb5c8daf-3237-4e5f-995c-3f8accf4e28d)



Asensin uudelle palvelimelle apache2.


![image](https://github.com/user-attachments/assets/fa918c8e-6629-4dfd-83db-cb4da498070a)



Testisivu ei kuitenkaan jostain syystä näy.



![image](https://github.com/user-attachments/assets/446d03fe-b38f-47e0-988c-6d0b94098acf)


Virhelokiinkaan en päässyt, onko niin ettei siellä ole vielä mitään tietoa?




![image](https://github.com/user-attachments/assets/d4d45f45-537c-419c-a302-ce32aca99d58)




Ilmeisesti apache2 oli kuitenkin toiminnassa.



![image](https://github.com/user-attachments/assets/e5b8852a-1edc-4cb9-be56-dcfac3e1c630)




Tätä en saanut nyt toimimaan, joten siirryin tässä kohtaa seuraavaan tehtävään.

**d)Laita omalle julkiselle palvelimellesi uusi Name Based Virtual Host.**	


**5.2.2025 15:25**


Siirryin tekemään name based virtual hostia.

![image](https://github.com/user-attachments/assets/b9fe58d7-3909-4cf0-8bcb-a054d51cab81)



Lisäsin tarvittavat tiedot.



![image](https://github.com/user-attachments/assets/35663369-fa85-447a-b078-7728bf16ce09)

![image](https://github.com/user-attachments/assets/24872937-36cc-4ef9-9736-75ac0bd63362)


![image](https://github.com/user-attachments/assets/3a7e15d2-60b4-4cb0-a309-40b5e110a295)



![image](https://github.com/user-attachments/assets/786b0f02-dc17-407a-b369-97d94aa1ca8c)



![image](https://github.com/user-attachments/assets/8ee557fc-1365-461d-9492-f1006a134608)



Verkkosivu ei kuitenkaan vieläkään toimi.



![image](https://github.com/user-attachments/assets/497761dc-0010-43cd-8b2c-903d355c9289)



Siirryin sudoedit /etc/hosts ja tajusinkin tässä kohtaa miksi sivu ei toimi. En hakenut localhostilla, vaan palvelimen IP-osoitteella, jota ei ole vielä osoitettu edes millekään verkkosivulle.
Kävin lisäämässä hosteihin testisivun.



![image](https://github.com/user-attachments/assets/161e630c-ccc9-40b5-98c5-31d453d7c900)


Sivua ei silti löydy…



![image](https://github.com/user-attachments/assets/d912f386-3c0f-406c-84ef-dbda1f4ae353)




Eikä löydy myöskään testisivun nimellä.



![image](https://github.com/user-attachments/assets/afa92a40-eb73-4aad-a76c-898538dcd0ac)






**6.2.2025 14:25**


Jatkoin tehtävää ja yritin ratkaista ongelmia verkkosivun kanssa.


Avasin Linux virtuaalipalvelimen ja tein heti päivitykset.




![image](https://github.com/user-attachments/assets/a0718299-9e05-4c2b-b749-616b55f1ce19)



Otin yhteyden UpCloud virtuaalipalvelimeen johon tein myös päivitykset.



![image](https://github.com/user-attachments/assets/76544348-559e-47a6-82e2-67e1fcf1afff)


![image](https://github.com/user-attachments/assets/67c0e99d-cdea-4341-b2a7-268da829a43f)


Kokeilin seuraavaksi pingata virtuaalipalvelimen IP-osoitetta.
Jostain syystä minut oli heitetty pihalle virtuaalipalvelimelta, joten otin uudelleen yhteyden palvelimeen, jonka jälkeen tein pingauksen.



![image](https://github.com/user-attachments/assets/0ea5cfea-5693-4e4f-922a-9f2f55d820da)



![image](https://github.com/user-attachments/assets/748ece14-f679-4a5b-9866-1c3fba7597db)



Pingaus näytti tuottavan tulosta ja tapoin komennon ctrl + c, koska tuloksia tuli koko ajan lisää.
Lähdin kokeilemaan selaimen puolelle toimiiko verkkosivu.



![image](https://github.com/user-attachments/assets/f75a0d37-037e-48a4-9898-4c9ec4d6d887)


Kokeilin seuraavaksi komentoa curl localhost:80, joka näyttää teksimuodossa mitä localhostin sivulla on.



![image](https://github.com/user-attachments/assets/aecb893b-7b5f-46ad-aaa4-1ba7d9347cc7)




Kokeilin seuraavaksi curl maariatesti.com



![image](https://github.com/user-attachments/assets/3cb149e0-dde8-400c-99ae-9d20a9bdd385)


Sieltä nähdäänkin, että sivulla on vain virhe.
Kävin vielä tarkistamassa sivun asetukset.


![image](https://github.com/user-attachments/assets/6a30adc3-3113-412b-a839-b51a2a2e3a75)




![image](https://github.com/user-attachments/assets/44c0abb3-cd5c-446b-931a-b42d47c17e25)




Nämä asetukset olivat mielestäni oikein.
Yritin ottaa virtualhostin uudelleen käyttöön.




![image](https://github.com/user-attachments/assets/1a2c7137-aca6-4fbb-a69c-afb7baf542d1)




Yritin käydä vielä katsomassa apachen error.logia




![image](https://github.com/user-attachments/assets/1958c961-689a-44ea-8c84-f2d9e1c54528)




Alin lokitieto viittaa, että joitain tarvittavia oikeuksia ei ole. Miten siis voisi edetä asian kanssa?


**Lähteet:** 


Susanna Lehto. 14.2.2022. Teoriasta käytäntöön pilvipalvelimen avulla(h4). https://susannalehto.fi/2022/teoriasta-kaytantoon-pilvipalvelimen-avulla-h4/. Luettu: 5.2.2025


Tero Karvinen. 19.9.2017. First Steps on a New Virtual Private Server – an Example on DigitalOcean and Ubuntu 16.04 LTS. https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/. Luettu: 5.2.2025


Tero Karvinen. Linux Palvelimet 2025 alkukevät. h4 Maailma kuulee. https://terokarvinen.com/linux-palvelimet/#h4-maailma-kuulee. Luettu: 5.2.2025


Tero Karvinen. 10.4.2018. Name Based Virtual Hosts on Apache – Multiple Websites to Single IP Address. https://terokarvinen.com/2018/04/10/name-based-virtual-hosts-on-apache-multiple-websites-to-single-ip-address/. Luettu: 5.2.2025



















