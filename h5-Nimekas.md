# h5 Nimekäs


## JOHDANTO


Tämä tehtävä oli moniosainen ja keskittyi julkisen nimen luomiseen ja sen osoittamiseen omaan, aikaisemmin luotuun palvelimeen. Tehtävä jatkui name based virtual hostin tekemiseen sekä muokkaamiseen ilman pääkäyttäjän oikeuksia.


Seuraavassa vaiheessa tehtiin vähintään kolmen erillisen alasivun kotisivu ja laittaa ne näkymään omalla palvelimella. Lisäksi piti tehdä kaksi alidomainia, jotka osoittavat omaan koneeseen. 


Lopuksi tutkittiin `host` ja `dig`komennoilla nimen DNS-tietoja. 


# a) Nimi


**12.2.2025 12:30**


Luennolla (11.2.2025 17:40-20:30) kävimme läpi domain nimen vuokraamisen NameCheapilta. Toimin esimerkkinä, ja opettajan ohjauksessa vuokrasin domainin.


Valitsin käyttää NameCheap palvelua opettajan suosituksesta, koska itsellä ei tästä aiheesta ollut aikaisempaa kokoemusta. Aloitin kirjautumalla NameCheapiin ja ostamalla haluamani domainin, valitsin alla näkyvän maariahakanpaa.com, joka sattui olemaan vapaana. Hintaa tälle tuli alle 10€/vuosi.


![image](https://github.com/user-attachments/assets/7ef87877-dcae-4cdf-892b-726245748df2)


![image](https://github.com/user-attachments/assets/c87c38b2-10e3-49d3-b028-3089032ae78d)


Maksun jälkeen siirryin ostamani domainin Dashboardille ja sieltä oikean reunan manage painikkeesta, pääsin tekemään haluamani muutokset.



![image](https://github.com/user-attachments/assets/d8c84356-e881-42b0-a5ff-bfe709102f11)


![image](https://github.com/user-attachments/assets/51c0de4a-d2c0-4309-a382-2e4ab3dcaf44)


Seuraavaksi valitsin yläreunan kuvakkeista ’Advanced DNS’. Valitsin ’add new record’, johon lisäsin A tietueeksi Hostille @, sekä Valueksi pilvipalvelimeni IP-osoitteen.
Tein myös toisen A tietueen, johon hostiksi laitoin www ja valueksi jälleen sen saman IP-osoitteen.



![image](https://github.com/user-attachments/assets/42743b52-4484-4e91-bc6b-444f2e82310b)



![image](https://github.com/user-attachments/assets/e33d180b-959b-479e-b5ee-7aea29979fa3)


Lisättyäni omat tietueeni, oletukseni olleet @ sekä www hostit katosivat. 


# b) Based


**12.2.2025 12:45**


Seuraavaksi siirryin virtuaalikoneelleni, ja otin yhteyden palvelimelle.


 ![image](https://github.com/user-attachments/assets/4aaec16f-0fc6-45a6-be65-2406384fdea9)



Kävin konfiguroimassa maariahakanpaa.com tiedostolle tarvittavat tiedot. Kopioin ne aikaisemmasta tekemästäni testisivusta.


![image](https://github.com/user-attachments/assets/a6bb3b4f-d2f8-4deb-9a32-39ed8b8351a8)



Tein maariahakanpaa.com sivustoa koskevat muokkaukset ServerNameen, ServerAliakseen, DocumentRoottiin sekä Directoryyn.


![image](https://github.com/user-attachments/assets/e88b7493-6849-4636-aee8-05a70a179d4c)





Seuraavaksi kävin käynnistämässä maariahakanpaa.com sivun.


![image](https://github.com/user-attachments/assets/002151ef-829f-4d92-a743-04fa70d5f7ea)


Sen jälkeen uudelleenkäynnistin apachen.


![image](https://github.com/user-attachments/assets/c512729c-45a8-4869-a284-c6828695c374)


Verkkosivu ei toiminut, minulla ei siitä tullut kuvaa, mutta näytti muistaakseni 403-erroria. Joten kävin tarkastamassa error.login.



![image](https://github.com/user-attachments/assets/e440fa46-ae96-4c24-b90f-ecc3c2af3257)


![image](https://github.com/user-attachments/assets/3119ad4c-3b0c-40b4-b28a-f25fb092806e)


Sieltä selvisi, ettei riittäviä oikeuksia ollut, joten kävin tarkistamassa kotikansion oikeudet.


![image](https://github.com/user-attachments/assets/06b006fa-7f3d-43bf-b56c-6e40f583885a)


Selvisi että, oikeudet olivat vain user maarialla, joten kävin lisäämässä execute- oikeudet myös muille käyttäjille eli groupille ja othersille.




![image](https://github.com/user-attachments/assets/627ed708-fd6a-4ac1-987d-5a028442b63b)



Seuraavaksi kävin taas tarkistamassa `sudo tail /var/log/apache2/error.log`



![image](https://github.com/user-attachments/assets/5bebb6f6-cb99-491a-87e5-78c74c047563)



Tässä virheessä tarkoitettiin serverin konfigurointiin liittyvää virhettä.


Kävin tarkistamassa maariahakapaa.com kansion, jota ei ollut vielä olemassa.



![image](https://github.com/user-attachments/assets/17e928bb-b803-4c29-9599-8898bc827e09)


public_sites kansiosta löytyi ainoastaan aiemmin tekemäni harjoitussivun kansio. Tein maariahakanpaa.comille uuden kansion.


![image](https://github.com/user-attachments/assets/774ff0ee-4ab0-4fd5-93ba-68d6ca2528fe)


Sitten kävin luomassa kansioon index.html tiedoston.


![image](https://github.com/user-attachments/assets/6f83406b-2418-4c0c-8ff5-b6b161cfaf29)


Muokkasin tiedostoon tunnistettavan tekstin, ja selaimessa laitettuani url- kenttään maariahakanpaa.com, niin tekemäni index.html tiedostossa oleva teksti näkyi kuten pitikin.



![image](https://github.com/user-attachments/assets/a0929fe4-1550-4721-9752-7a4b2284b6f6)


# C) Kotisivu


**12.2.2025 13:10**


Aloitin muokkaamalla jo valmiina olevaa index.html tiedostoa komennolla `micro index.html`




![image](https://github.com/user-attachments/assets/1020cc77-33c3-4ed3-a672-5394f4d8b061)


HTML tiedosto näytti tältä, lisäsin otsikon, tekstikappaleen, sekä kuvan netin ilmaisesta kuvapankista(pixabay). Lisäsin myös footer elementin sivun alimmaiseksi, josta näkee koska olen sivun viimeksi tarkistanut.
Selaimella sivu näytti tältä:



![image](https://github.com/user-attachments/assets/cfade96d-8ca1-45cc-8787-ef4684944d11)


Sivusto näkyy siis selaimessa millä tahansa laitteella katsottaessa. Kokeilin omalla kannettavalla tietokoneella, virtuaalikoneella sekä puhelimella.

Seuraavaksi tein blog.html tiedoston. `micro blog.html`


Tein sivustolle Matkablogin, johon listasin kaikkia maat joissa olen tähän mennessä vieraillut.


HTML tiedosto näytti tältä:


![image](https://github.com/user-attachments/assets/4b9566ed-6d1d-49e9-8875-30667c3ca2ab)


Lisäsin tiedostoon otsikon ja tekstikentän lisäksi kuvan (pixabay) sekä lista-elementin, jonka sisälle listasin maat ja vuosiluvut. Tälle sivulla lisäsin myös viimeiseksi footer-elementin.
Selaimessa sivu näytti tältä:



![image](https://github.com/user-attachments/assets/d20725fa-30a6-4a1a-aca1-a4f68493b069)



Viimeiseksi tein projects.html tiedoston `micro projects.html`



![image](https://github.com/user-attachments/assets/ccb72101-a257-426c-b45a-ca07e6946681)


Tälle sivulle tein edellisten tapaan otsikon, tekstikentän sekä lisäsin taulukon, johon sijoitin tämänhetkiset projektit. Alapuolelle lisäsin footer-elementin.


Jokaiseen HTML tiedostoon lisäsin navigointi elementin, jonka avulla sivujen välillä pystyy helposti siirtyä. Tein tämän sivuston kaikki html tiedostot maariahakanpaa.com kansion alle, joten navigointi onnistuu näin helposti.


# d) Alidomain


**13.2.2025 10:45**


Menin ensimmäiseksi NameCheapin verkkosivuille ja kirjauduin sisään. Menin dashboardille oman domainin manage-asetuksiin, josta saan lisättyä alidomainit. Valitsin Advanced DNS välilehden.


Tein A tietueelle alidomainin ja osoitin sen samaan virtuaalipalvelimen IP-osoitteeseen, mihin päädomainkin osoittaa. Tein myös CNAME- tietueelle alidomainin ja laitoin sen osoittamaan päädomain osoitteeseen.


![image](https://github.com/user-attachments/assets/17075287-2bc1-453c-87a5-6e679015e563)


Testasin sivuja selaimessa.


![image](https://github.com/user-attachments/assets/c739600b-b452-4b7b-9437-23a4d9297231)


A tietueen sivu toimii, mutta sivulle tulee aikanaan oletusselaimeen tekemäni index.html sivu.



![image](https://github.com/user-attachments/assets/6f4ba3c3-7e09-4837-a6ad-6633e4f4d4fc)



CNAME tietueen sivu myös toimii, ja siinäkin tulee sama oletusselaimen index.html sivu.


Käyn muokkaamassa sivuja niin, että ne avaavat myös päädomainin sivun.


Siirryin virtuaalikoneelleni ja aloitin päivittämällä sen, jonka jälkeen otin yhteyden virtuaalipalvelimelle, ja tein päivitykset.


Kävin muokkaamassa maariahakanpaa.copm.conf tiedostoa, johon lisäsin aliakset. Löysin tähän vinkin toisen opiskelijan rapostista. (https://github.com/jaolim/linux-servers/blob/main/h5_Nimekas.md)


![image](https://github.com/user-attachments/assets/a2aebb60-272e-46a4-b511-9f44306c4173)


Tämän jälkeen suoritin komennon `sudo systemctl restart apache2` , jotta tekemäni muutokset päivittyisivät.


Tarkistin asian selaimessa, CNAME alidomain toimii:


![image](https://github.com/user-attachments/assets/deb69eda-5f0c-4877-886a-efa50a66c417)



A tietueen alidomain näyttää edelleen oletussivua:


![image](https://github.com/user-attachments/assets/452082fb-81e1-49f4-ae00-9b880d7e9ace)


Kävin lisäämässä conf tiedostoon vielä A tietueen erikseen.


![image](https://github.com/user-attachments/assets/fc1b9972-bbd1-473b-8e65-3a244ea02c65)

`sudo systemctl restart apache2` uudelleen, ja nyt myös A tietueen alidomain ohjautuu päädomainin sivulle.


![image](https://github.com/user-attachments/assets/3f8e11c1-4cdb-41d1-977a-fee3d31f3164)



Lisätehtävänä lähdin luomaan A tietueen alidomainille, eli blog.maariahakanpaa.comille omaa name based virtual hostia.


Aloitin `sudoedit blog.maariahakanpaa.com.conf` jonne muokkasin .conf tiedoston.


![image](https://github.com/user-attachments/assets/19265b9b-9a3c-4ac3-a897-d4ea5bc7c1d4)



Seuraavaksi käynnistin sen komennolla `sudo a2ensite blog.maariahakanpaa.com` sekä käynnistin apachen uudelleen `sudo systemctl restart apache2`


Kävin heti selaimessa katsomassa, ja blog.maariahakanpaa.com ei enää yhdisty päädomainin sivuun.


![image](https://github.com/user-attachments/assets/ade94e90-d3ca-4f1c-b174-6d99a444d0f2)


Kävin luomassa public_sites kansioon uuden kansion uudelle name based virtual hostille.



![image](https://github.com/user-attachments/assets/8ab032f0-cba2-4caa-b617-782d9a6bd86f)


Seuraavaksi tein index.html tiedoston, johon kirjoitin lyhyen  kuvauksen sivusta


![image](https://github.com/user-attachments/assets/ef0e0e12-3cd5-4d1f-b22c-bca77788434b)


Selaimessa sivu ei vielä toiminut.


![image](https://github.com/user-attachments/assets/c17c2084-7a06-4afc-aa4d-da86b04405f8)


Kävin katsomassa error.login `sudo tail /var/log/apache2/error.log` ja huomasinkin kirjoitusvirheen kansion nimessä.


![image](https://github.com/user-attachments/assets/80840792-61b3-4dfe-afea-9c85144fd0d8)


Kävin korjaamassa sites-available kansiossa blog.maariahakanpaa.com.conf tiedostosta kirjoitusvirheet. Siellä oli myös toinen kirjoitusvirhe tiedostopolussa, jonka korjasin, /home/xubuntu /home/maaria.



![image](https://github.com/user-attachments/assets/634e0888-c2ae-4251-9807-0a5d9c4ca192)


Varmuuden vuoksi `sudo systemctl restart apache2`


Nyt kun kirjoitusvirheet tiedostopolussa oli korjattu niin sivu toimi selaimessa!



![image](https://github.com/user-attachments/assets/dc8a3d10-da0e-42dc-96d7-d30dd02c9a2d)



Huomasin kuitenkin että url:ssa oli blog.maariahakanpaa.com/index.html eikä sivu toiminut ilman tuota index.html lisäystä tuolla lopussa.


Kävin poistamassa blog.maariahakanpaa.com Aliaksen maariahakanpaa.com.conf tiedostosta, johon sen oli aiemmin lisännyt. Jätin sinne aliakseksi vain *.maariahakanpaa.com, joka viittaa CNAME tietueeseen eli page.maariahakanpaa.comiin.


![image](https://github.com/user-attachments/assets/5fe6d996-fb49-424d-9239-5eb58cb93bd0)



Uudelleenkäynnistin apachen ja tarkistin selaimessa, nyt blog.maariahakanpaa.com name based virtual host toimii kuten pitää.



![image](https://github.com/user-attachments/assets/838901f0-fc7d-44d4-9783-3dc04622dfdf)



Tein vielä html- koodin tarkistuksen.



![image](https://github.com/user-attachments/assets/b1f08988-6e8c-466d-b84b-862bbf797025)



Kävin poistamassa html tiedoston footer-osuudesta ylimääräisen ’</div>’ elementin, joka oli jostain syystä tullut sinne kahteen kertaan.

Kävin myös tarkistamassa alidomainin html tiedoston.



![image](https://github.com/user-attachments/assets/02cd380d-bc4a-4a9c-bb39-5323b5969f61)


Koska olin tehnyt sivun vain testimielessä, en ollut lisännyt sinne mitään html- elementtejä, ja lisäsin sinne nyt perusrungon.


![image](https://github.com/user-attachments/assets/553d58ca-c843-4157-8d70-1d4855d40c02)


# e) Tutki jonkin nimen DNS-tietoja 'host' ja 'dig' -komennoilla.


**13.2.2025 13:40**


Asensin `sudo apt-get install dnsutils` , jolla pääsen käyttämään mm. dig komentoa. Löysin komennon googlaamalla, debianin packages sivulta.


## OMA DOMAIN



![image](https://github.com/user-attachments/assets/39c91b1e-d4ef-404b-88f2-4348c3c66df1)


**has address** = kertoo domainin IPv4-osoitteen


**mail is handled by** = kertoo mitkä palvelimet käsittelevät sivuston sähköpostiliikennettä (eforward-registrar-servers).


Seuraavaksi kokeilin `dig` komentoa:


![image](https://github.com/user-attachments/assets/28f0d95f-98c5-4f90-848d-dc49e2926b0d)


`dig` tekee kyselyn maariahakanpaa.com:in IP-osoitteeseen, ja saa sieltä vastauksen.


**>>Header<<- opcode: QUERY, status: NOERROR** = tarkoittaa että DNS vastaus onnistui.


**QUESTION SECTION** = Haettu tieto, tässä tapauksessa A-tietue.


**ANSWER SECTION** = Palautettu IPv4-osoite (93.184.216.34) ja TTL (TIME-TO-LIVE) (86207 sekuntia).


**Query time** = Haku kesti 0 ms.


**SERVER** = DNS-palvelin, jolta tieto saatiin (94.237.127.9).


## PIKKUYRITYKSEN DOMAIN



![image](https://github.com/user-attachments/assets/251c5731-5719-493e-9b17-97d21140b4d1)


valotarshop.fi on pieni kosmetiikka-alan yritys, jolla on kaksi kivijalkamyymälää sekä verkkokauppa.


**has address** = kertoo domainin IPv4-osoitteen.


**has IPv6 address** = kertoo yrityksen IPv6 osoitteen.


**mail is handled by** = kertoo mitkä palvelimet käsittelevät sivuston sähköpostiliikennettä (google).



![image](https://github.com/user-attachments/assets/e4e70579-3623-42fb-a14c-75721ea3ea95)


`dig` tekee kyselyn valotarshop.fi:n IP-osoitteesen, ja saa sieltä vastauksen.


**>>Header<<- opcode: QUERY, status: NOERROR** = tarkoittaa että DNS vastaus onnistui.


**QUESTION SECTION** = Haettu tieto, tässä tapauksessa A-tietue.


**ANSWER SECTION** = Palautettu IPv4-osoite (91.216.90.78) ja TTL (TIME-TO-LIVE) (3556 sekuntia).


**Query time** = Haku kesti 0 ms.


**SERVER** = DNS-palvelin, jolta tieto saatiin (94.237.127.9).


## SUUREN YRITYKSEN DOMAIN



![image](https://github.com/user-attachments/assets/993d459b-83cd-412e-a1f1-412d49452552)


**has address** = kertoo domainin IPv4-osoitteen, joita on 4 kappaletta.


**has IPv6 address** = kertoo yrityksen IPv6 osoitteen, joita on 8 kappaletta.


**mail is handled by** = kertoo mitkä palvelimet käsittelevät sivuston sähköpostiliikennettä (outlook).


![image](https://github.com/user-attachments/assets/6b82d62e-3f04-479f-8b82-1bac7a154250)


`dig` tekee kyselyn iltalehti.fi:in IP-osoitteesen, ja saa sieltä vastauksen.


**>>Header<<- opcode: QUERY, status: NOERROR** = tarkoittaa että DNS vastaus onnistui.


**QUESTION SECTION** = Haettu tieto, tässä tapauksessa A-tietue.


**ANSWER SECTION** = Palautettu IPv4-osoite (18.165.140.74 JA 18.165.140.71 JA 18.165.140.7 JA 18.165.140.91) ja TTL (TIME-TO-LIVE) (60 sekuntia).


**Query time** = Haku kesti 12 ms.


**SERVER** = DNS-palvelin, jolta tieto saatiin (94.237.127.9).


# LÄHTEET


Tero Karvinen. Linux Palvelimet 2025 alkukevät. https://terokarvinen.com/linux-palvelimet/. Luettu: 13.2.2025


Tero Karvinen. 12.2.2012. Short HTML5 page.  https://terokarvinen.com/2012/short-html5-page/. Luettu: 13.2.2025


Kodarit. HTML OPAS. https://kodarit.com/fi/html-opas/


Pixabay. https://pixabay.com/fi/photos/kvalvika-beach-ocean-norway-meri-4880055/. Luettu: 13.2.2025


GitHub/danielck. html.pohja. https://gist.github.com/danielck/1993436. Luettu: 13.2.2025


w3schools. HTML <nav> Tag. https://www.w3schools.com/Tags/tag_nav.asp. Luettu: 13.2.2025


dnsimple. Differences Between A and CNAME Records https://support.dnsimple.com/articles/differences-a-cname-records/. Luettu: 13.2.2025


NameCheap. How to Create a Subdomain for my Domain https://www.namecheap.com/support/knowledgebase/article.aspx/9776/2237/how-to-create-a-subdomain-for-my-domain/. Luettu: 13.2.2025


debian. https://packages.debian.org/buster/dnsutils. Luettu: 13.2.2025


Github/jaolim. h5 Nimekäs. https://github.com/jaolim/linux-servers/blob/main/h5_Nimekas.md. Luettu: 13.2.2025


W3C. Markup Validation Service. https://validator.w3.org/. Luettu: 13.2.2025


Azion. How to look up DNS servers with Dig command. https://www.azion.com/en/documentation/products/guides/run-the-dig-command/. Luettu: 13.2.2025





