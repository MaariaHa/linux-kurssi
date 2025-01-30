# h3 Hello Web Server

## Johdanto
Tämän tehtävä piti sisällään kahden artikkelin tiivistämisen. Tehtävän seuraavissa osissa testattiin weppipalvelimen toimivuutta, analysoitiin access.login rivejä, tehtiin uusi name based virtual host, tehtiin HTML5 sivu, ja kokeiltiin curl komentoja. Lisätehtävissä hankittiin GitHub Education paketti sekä laitettiin tietokone vastaamaan kahdella eri sivullla ja kahdesta eri nimestä.

**30.1.2025 10:00**
**Name-Based Virtual Host Support**
-	IP-pohjaisissa virtuaalipalvelimissa palvelin käyttää yhteyden IP-osoitetta oikean virtuaalipalvelimen tunnistamiseen. Tämän vuoksi jokaiselle isäntänimelle tarvitaan oma IP-osoite.
-	Nimipohjaisissa (name-based) virtuaalipalvelimissa palvelin luottaa siihen että asiakas ilmoittaa hostnimen http-otsikoiden mukana.
-	Nimipohjainen helpompi toteuttaa, koska riittää että DNS palvelin on konfiguroitu ohjaamaan kukin hostnimi oikeaan IP osoitteeseen, ja Apache http serveri tunnistaa eri hostnimet.
-	Kun pyyntö saapuu, palvelin etsii parhaiten (tarkimmin) vastaavan <VirtualHost>:in perustuen pyynnössä käytettyyn IP-osoitteeseen ja porttiin.
-	Jos useampi virtuaalipalvelin sisältää tämän parhaan IP-osoite + porttiyhdistelmän, Apache vertaa lisäksi ServerName- ja ServerAlias määreitä pyynnössä olevaan palvelinnimeen.
-	Jos yksikään ServerName- tai ServerAlias-määreistä ei vastaa pyynnön sisältämää palvelinnimeä, käytetään ensimmäisenä määriteltyä virtuaalipalvelinta, joka vastaa kyseistä IP-osoite- ja porttiyhdistelmää.
Lähde: Apache. Name-based Virtual Host Support.

**Name Base Virtual Hosts on Apache – Multiple Websites to Single IP Address**
-	Apachen avulla, yhdelle IP osoitteelle voi olla monta domain nimeä.
-	Seuraavilla komennoilla ja konfiguroinneilla saa luotua nimipohjaisen virtuaalipalvelimen komentorivikäyttöliittymässä:
o	Asenna ja konfiguroi webbiserveri korvaamalla oletusverkkosivut
 *	$ sudo apt-get -y install apache2
 *	$ echo "Default"|sudo tee /var/www/html/index.html
o	Lisää uusi nimipohjainen virtuaalipalvelin
 *	$ sudoedit /etc/apache2/sites-available/kissa.example.com.conf
 *	$ cat /etc/apache2/sites-available/kissa.example.com.conf
 *	 ServerName kissa.example.com
 *	 ServerAlias www.kissa.example.com
 *	 DocumentRoot /home/maaria/publicsites/kissa.example.com
 *	 /home/maaria/publicsites/kissa.example.com>
 *	Require all granted
 *	Alkuun ja loppuun tulee VirtualHost sekä Directory elementit
 *	$ sudo a2ensite kissa.example.com
 *	$ sudo systemctl restart apache2
o	Luo uusi weppisivu normaali käyttäjänä
 *	mkdir -p /home/maaria/publicsites/kissa.example.com/
 *	$ echo kissa > /home/maaria/publicsites/kissa.example.com/index.html
o	Testaa
 *	$ curl -H 'Host: kissa.example.com' localhost
 *	$ curl localhost
Samalle IP-osoitteelle voi siis lisätä niin monta virtual hostia kuin haluaa.
Lähde: Tero Karvinen.10.4.2018.Name Based Virtual Hosts on Apache -  Multiple Websites to Single IP Address.


**30.1.2025 10:45**
a) Testaa, että weppipalvelin vastaa localhost-osoitteesta.


Apache weppipalvelin asennettiin luennon (28.1.2025 17:40-20:30) aikana, sain silloin opiskelijakollegoiden sekä opettajan avustuksella myös weppisivun palvelimelta toimimaan. 
Ensimmäiseksi suoritin perinteisen sudo apt-get update pakettien päivitys komennon.
Seuraavaksi lähdin tarkistamaan, onko apache palvelin käynnissä.

![image](https://github.com/user-attachments/assets/ea329229-f3d3-46ad-a872-852f42981cbd)


Kaikki näytti olevan tältä osin kunnossa.
Seuraavaksi lähdin testaamaan, vieläkö toissapäivänä luomani webbipalvelin on käynnissä. Kirjoitin virtuaalikoneen selaimen url-kenttään: http://localhost

![image](https://github.com/user-attachments/assets/7826fee4-4d45-46b7-b220-99ee98565003)



localhostista tulee vastaus, joten weppipalvein näytti olevan käynnissä ja toimivan edelleen.

**30.1.2025 11:00**


b) Etsi lokirivit, jotka syntyvät kun palvelimelta lataa sivun.


Kokeilin vielä curl komennolla palvelimen toimivuutta komentokehoitteessa harjoituksen vuoksi.


![image](https://github.com/user-attachments/assets/14a8805a-2250-4a13-aba4-f23d73982ccd)


Seuraavaksi lähdin tarkastelemaan tapahtumalokia, ja jostain syystä sieltä näkyi vain toissapäiväiset tapahtumat. Olin kuitenkin käynyt myös 30.1. localhostissa ja päivittänyt siellä sivun, mutta tämän päivän tapahtumia siellä ei näkynyt.
Joka tapauksessa, tarkastelin lähemmin loki rivejä.


127.0.0.1 - - [28/Jan/2025:20:13:15 +0200] ”GET / http/1.1” 200 3380 ”-” ”Mozilla/5.0 (x11; Linux x86_64; rv:128.0) Gecko /20100101 Firefox/128.0”


**127.0.0.1** :arrow_right: Localhostin IP- osoite


**"- -"**  :arrow_right: Identifioi hostin, eli toisinsanoen, minun oman koneen. Tässä tapauksessa sille ei ollut mitään tarkempaa nimeä tai määritelmää annettu.
 
 
**[28/Jan/2025:20:13:15 +0200]** :arrow_right: Tapahtuman päivämäärä ja kellonaika, viimeisinä numeroina + jälkeen tarkoittaa UTC +2, joka on siis Suomen aikavyöhyke näin talvella.


**”GET / http/1.1”** :arrow_right: HTTP pyyntö


**200 3380** :arrow_right: HTTP statuskoodi, 200=ok, toinen numero on vastauksen koko tavuina


**”-”** :arrow_right: Lähettäjä, tämä kohta on tyhjä


**Mozilla/5.0** :arrow_right: Käyttäjäagentti


**(x11** :arrow_right: Käyttöjärjestelmän graafinen järjestelmä


**Linux x86_64** :arrow_right: Käyttöjärjestelmä ja sen arkkitehtuuri, 64-bittinen Linux


**rv:128.0** :arrow_right: Firefoxin versio


**Gecko** :arrow_right: Firefoxin käyttämä selainmoottori


**20100101** :arrow_right: Päivämäärä viittaa Gecko-  moottorin tunnukseen, eikä vastaa tämän hetkistä päivää


**Firefox/128.0”**  Selain ja sen tarkka versio


127.0.0.1 - - [28/Jan/2025:20:13:16 +0200] "GET /icons/openlogo-75.png HTTP/1.1" 200 6040”http://localhost/” ”Mozilla/5.0 (x11; Linux x86_64; rv:128.0) Gecko /20100101 Firefox/128.0”


**GET /icons/openlogo-75.png** :arrow_right: Tämä on pyyntö Apache palvelimelta, tiedostoa nimeltä openlogi-75.png haetaan kansiosta icons.


**200** :arrow_right: HTTP kuittaus


**6040** :arrow_right: tiedoston koko tavuina


**http://localhost/** :arrow_right: Lähettäjä on tässä tilanteessa localhost palvelin


127.0.0.1 - - [28/Jan/2025:20:13:15 +0200] ” GET /favicon.ico HTTP/1.1” 404 407 ”http://localhost/” ”Mozilla/5.0 (x11; Linux x86_64; rv:128.0) Gecko /20100101 Firefox/128.0”


**GET /favicon.ico**  :arrow_right: HTTP pyyntö, jolla haetaan selaimen oletuksena pyytämää tiedostoa, selaimet hakevat sen automaattisesti kun verkkosivu ladataan


**404** :arrow_right: Vikakoodi, ”not found”


**407** :arrow_right: vastauksen sisällön koko tavuina


**http://localhost** :arrow_right: sivu jolta pyyntö tehtiin


Lähteitä, josta sain apuja lokirivien tulkitsemiseen:

https://www.sumologic.com/blog/apache-access-log/

https://httpd.apache.org/docs/2.4/logs.html

https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/User-Agent

https://www.keycdn.com/support/apache-access-log


**30.1.2025 13:14**


c) Etusivu uusiksi. Tee uusi name based virtual host. Sivun tulee näkyä suoraan palvelimen etusivulla http://localhost/. Sivua pitää pystyä muokkaamaan normaalina käyttäjänä, ilman sudoa. Tee uusi, laita vanhat pois päältä. Uusi sivu on hattu.example.com, ja tämän pitää näkyä: asetustiedoston nimessä, asetustiedoston ServerName-muuttujassa sekä etusivun sisällössä.

Aloitin tehtävän avaamalla editorin komennolla:
sudoedit /etc/apache2/sites-available/hattu.example.com.conf
Kirjoitin sinne konfigurointiin tarvittavat tiedot, Tero Karvisen Add New Name Based Virtual Host ohjeen mukaan.


![image](https://github.com/user-attachments/assets/2737af30-9992-426e-848a-d1c446586f08)


Seuraavaksi sammutin olemassa olevan maaria.example.com, jotta voisin käynnistää harjoituksessa vaadittavan hattu.example.com sivuston.



![image](https://github.com/user-attachments/assets/482f9632-7928-4d95-b302-4c882b4406ff)


Edellinen harjoitussivusto on nyt suljettu, kävin vielä selaimen puolella testaamassa asian.


![image](https://github.com/user-attachments/assets/c1035b43-828c-4c62-96d8-0d3201de35f5)


Default sivu oli mennyt päälle.


Seuraavaksi käynnistetään harjoitussivu hattu.example.com


![image](https://github.com/user-attachments/assets/35881e80-dd1a-4734-b9a5-1d665bc757ce)



Näytti olevan ok. Sitten tarvitsin vielä index.html tiedoston, jotta sivulla näytetään mitä tehtävänannossa pyydetään.


![image](https://github.com/user-attachments/assets/fed847b5-a7c4-40c1-9df6-68fe1b90608e)


Kokeilin ensin title- elementtiä, mutta jostain syystä sivusto ei näyttänyt mitään.


![image](https://github.com/user-attachments/assets/863fca43-afdf-4157-be4e-a61b3b040794)


Vaihdoin sen p- elementtiin, jolloin sain tekstin näkyville.


![image](https://github.com/user-attachments/assets/840c88dc-9a64-4bf4-accb-1404ec6256d0)



hattu.example.com oli onnistuneesti asetettu toimintakuntoon.


![image](https://github.com/user-attachments/assets/30fdeb49-9eab-4420-b747-026338286e86)



**31.1.2025 klo 13:56**


e) Tee validi HTML5 sivu.


Edellisestä HTML-kurssista oli ehtinyt kulua jo reilu vuosi, joten kävin muistelemassa miten HTML5 sivun rakenne menikään. Löysin (https://punomo.fi/html5-ja-web-sivun-rakenne/) hyvän lähteen mistä pääsin rakentamaan elementtejä sivulle. 


![image](https://github.com/user-attachments/assets/eb103c43-dcc7-4abc-8be5-3644be577434


Tein todella yksinkertaisen sivun, mutta siinä löytyi otsikko, kuva sekä pari tekstikappaletta. Kuvan hain pixabaysta, ilmaisesta kuvapankista, kuva löytyi yllättäen hakusanalla hattu. Kuvatiedostolle tein oman kansion, mkdir hattu.example.com kansion alle.


![image](https://github.com/user-attachments/assets/b117d0df-818f-457d-ae95-a17632342726)


Tältä sivu näyttää selaimessa.



![image](https://github.com/user-attachments/assets/1722a73a-f8c5-440a-a863-802cd0f1d81b)


**30.1.2025 14:20**


f) Anna esimerkit curl -l sekä curl komennoista. Selitä curl -l muutamasta näyttämästä otsakkeesta, mitä ne tarkoittavat.


curl -I localhost näyttää erilaista tietoa localhostista.


HTTP on localhostin käyttämä protokolla, ja kuten aikaisemmastakin tehtävästä tuli selville, 200, on HTTP:n kuittaus, ok.


Date kertoo ajan jolloin palvelin lähetti vastauksen


Server on palvelimen ohjelmisto(Apache) sekä versio (Debian)


Last-Modified: Koska tiedostoa on viimeksi muokattu


ETag on palvelimen verkkosivulle antaman tunniste, joka edustaa sivun tiettyä versiota. Jos tiedostoon ei ole tullut muutoksia, sivuston lataaminen on nopeampaa koska palvelimen ei tarvitse lähettää sitä uudelleen.


![image](https://github.com/user-attachments/assets/30ac5be6-474b-45cc-b69c-f78644cefdd6)


curl localhost näyttää localhostin html- sisällön tekstimuotoisena.


![image](https://github.com/user-attachments/assets/f99f7768-fcfc-408f-b280-46863d11aa08)


**30.1.2025 14:35**


m) Hanki GitHub Education paketti.
Laitoin GitHub Education hakemuksen sisään ja GitHub ei hyväksynyt ensimmäistä hakemustani, joten laitoin uuden ja odotan vahvistusta. Uskon että tässä muutaman päivän kuluessa saan asian eteenpäin.


**30.1.2025 15:00**


o) Vapaaehtoinen, vaikea: Laita sama tietokone vastaamaan kahdellla eri sivulla kahdesta eri nimestä. Eli kaksi weppisiteä samalla koneelle, esim. foo.example.com ja bar.example.com. Voit simuloida nimipalvelun toimintaa hosts-tiedoston avulla.


Kävin lisäämässä molemmat sivut /etc/hosts tiedostoon, Tero Karvisen ohjeen mukaan. Sivut on lisätty samalle IP-osoitteelle, joka on locahostin osoite.


![image](https://github.com/user-attachments/assets/99a41a2d-4d35-4ab1-a6b5-4ba02fdea67b)


Koska aikaisemman harjoituksen takia olin käynyt sulkemassa maaria.example.com sivuston, kävin avaamassa sen nyt uudelleen.


![image](https://github.com/user-attachments/assets/f18ed4d2-5e24-4bf5-919c-d57531bd9dc7)


Alemmassa kuvassa olin avannut molemmat sivut vierekkäin, eli ratkaisu näytti toimivan! Nyt minulla on kaksi toimivaa weppipalvelinta, ja tarvittaessa voin samalla tekniikalla luoda niitä lisää.


![image](https://github.com/user-attachments/assets/379d8ab1-1ed7-4263-ba57-d39584ac97cf)


**30.1.2025 15:35**


Sain kulutettua tehtäviin melkein koko päivän. Tehtävät olivat hieman työläitä, koska asia on niin uutta. Kuitenkin hyvien ohjeiden, ja tunnilla käytyjen tehtävien kautta, pääsin toivottuun lopputulokseen ja sain kaikki vaadittavat ratkaisut toimimaan. Olin myös tyytyväinen viimeisen vapaaehtoisen tehtävän ratkaisuun. GitHub Education asia jäi toistaiseksi auki, koska uutta vahvistusta en ole vielä saanut.



## Lähteet: 


Apache. Name-based Virtual Host Support. https://httpd.apache.org/docs/2.4/vhosts/name-based.html. Luettu 30.1.2025


Tero Karvinen.10.4.2018.Name Based Virtual Hosts on Apache -  Multiple Websites to Single IP Address. https://terokarvinen.com/2018/04/10/name-based-virtual-hosts-on-apache-multiple-websites-to-single-ip-address/. Luettu. 30.1.2025


sumo logic. 14.1.2020. Understanding the Apache Access Log: View, Locate and Analyze. https://www.sumologic.com/blog/apache-access-log/. Luettu: 30.1.2025


Apache. Log Files. https://httpd.apache.org/docs/2.4/logs.html. Luettu: 30.1.2025

mdn web docs. User-Agent. https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/User-Agent. Luettu. 30.1.2025


keycdn. 4.10.2018. Understanding the Apache Access Log. https://www.keycdn.com/support/apache-access-log. Luettu: 30.1.2025

punomo. 4.3.2018HTML5 ja Web-sivun rakenne. https://punomo.fi/html5-ja-web-sivun-rakenne/. Luettu: 30.1.2025

pixabay. https://pixabay.com/








