# Johdanto


Tämän tehtävän tarkoituksena oli tehdä tiivistelmät kolmesta artikkelista. Lisäksi hankittiin ja asennettiin omalle aiemmin luodulle palvelimelle ilmainen TLS.sertifikaatti Let’s Encryptilta ja varmistettiin sen toimivuus. Tämän sertifikaatin asennuksen jälkeen oli tarkoitus testata sivu laadunvarmistustyökalulla, esimerkiksi SSLLabs. Vapaaehtoisena tehtävänä oli luoda webbilomake johon laitetaan käyttäjätunnus ja salasana.

## x) Lue ja tiivistä.


Let's Encrypt 2024: How It Works


•	Let’s Encrypt ja ACME-protokolla mahdollistavat HTTPS-palvelimen automaattisen varmenteen hankinnan. 
•	Tämä tapahtuu ajamalla hallintaohjelmaa palvelimella, joka tunnistetaan julkisen avaimen avulla.
•	Agenttiohjelmisto luo avainparin ja todistaa hallintansa example.comiin suorittamalla CA:n haasteen, kuten lisäämällä DNS-tietueen tai luomalla HTTP-tiedoston.
•	Onnistuneen todennuksen jälkeen agentti saa oikeuden hallita varmenteita. 
•	Se voi pyytää, uusia ja perua varmenteita allekirjoittamalla hallintaviestit valtuutetulla avainparilla. 
•	Varmennetta varten se luo PKCS#10-pyynnön, allekirjoittaa sen ja lähettää CA:lle, joka tarkistaa pyynnön, myöntää varmenteen ja tallentaa sen Certificate Transparency -lokitietoihin.
•	Varmenteen perumiseksi agentti allekirjoittaa perumispyynnön, jonka CA tarkistaa ja julkaisee perumistiedot, jotta selaimet tietävät mitätöidä varmenteen.


Lange 2024: Lego: Obtain a Certificate: Using an existing, running web server


•	Jos palvelin toimii jo portissa 80, --http-vaihtoehto vaatii myös --http.webroot-vaihtoehdon. 
•	Tämä tallentaa http-01-haasteen tunnisteen määritettyyn hakemistoon .well-known/acme-challenge, mutta ei käynnistä palvelinta.
•	Hakemiston on oltava julkisesti saatavilla /-polkuna verkkotunnuksilla, jotta varmennus onnistuu. Jos se ei ole, pyynnöt on ohjattava uudelleen tähän hakemistoon.
•	Voi käyttää olemassa olevaa palvelinta ja antaa lego-työkalun kirjoittaa haasteavaimen seuraavasti: ’ lego --accept-tos --email you@example.com --http --http.webroot /polku/webrootiin --domains example.com run’


The Apache Software Foundation 2025: Apache HTTP Server Version 2.4 [Official] Documentation: SSL/TLS Strong Encryption: How-To: Basic Configuration Example


•	SSL konfiguraatiossa täytyy olla vähintään seuraavat asetukset:


’ LoadModule ssl_module modules/mod_ssl.so

Listen 443
<VirtualHost *:443>
    ServerName www.example.com
    SSLEngine on
    SSLCertificateFile "/path/to/www.example.com.cert"
    SSLCertificateKeyFile "/path/to/www.example.com.key"
</VirtualHost>’


## a)	Let’s. Hanki ja asenna palvelimellesi ilmainen TLS-sertifikaatti Let's Encryptilta. Osoita, että se toimii.


## 26.2.2025 klo 12:30


Tein TLS-sertifikaatin asentamisen luennolla 25.2.2025 opettajan ohjauksessa. 
Aloitin kirjautumalla virtuaalipalvelimelle.


![image](https://github.com/user-attachments/assets/918872ec-487a-4460-8249-e65d1912263f)




Heti kirjauduttuani tein tarvittavat päivitykset ’sudo apt-get update’ . Seuraavaksi asennettin lego ’sudo apt-get install lego’
Tämän avulla saadaan sertifikaatti asennetuksi ja HTTPS protokolla toimimaan verkkosivullani maariahakanpaa.com.
Seuraavaksi haettiin Let’s Encrypt sivustolta asennuspaketti.
Verkkosivu löytyi google-haulla ’let’s encrypt staging’ ja ensimmäinen hakutulos oli Staging Environment. Sieltä sain ACME URLin alla olevaan komentoon. URL käyttää testiympäristöä ja tarkoitettu virheiden etsintää varten. Tämä vaihe varmistaa, että prosessi toimii oikein ennen kuin siirrytään oikeisiin varmenteisiin.




![image](https://github.com/user-attachments/assets/23a3d0d4-30be-463e-b8f8-854d77797f8a)




Tämän asennuksen jälkeen oli luotu lego kansio oman käyttäjäni hakemistoon. Kävin tarkistamassa tiedostot sen sisältä.




![image](https://github.com/user-attachments/assets/039fbc06-a31c-4f71-93f3-553d0c91f9c9)




Muutin kansion nimen lego > dislego kansion ja tein uuden lego kansion. Kopioin dislego kansion sisällön lego kansioon. Eli yläpuolella kuvassa näkyvät tiedostot.




![image](https://github.com/user-attachments/assets/60da697b-0af8-47ab-8d64-ea8212647851)



Sitten suoritin lego komennon uudelleen ilman URLia. Kun aikaisemmin testiympäristössä varmistin ettei tule virheitä, niin siirryin varsinaiseen varmenteiden myöntämiseen.




![image](https://github.com/user-attachments/assets/4fcb47ab-3300-4ee2-ae24-7a82f89ef5d2)



Seuraavaksi muokkasin verkkosivun konfiguraatiotiedostoa.


![image](https://github.com/user-attachments/assets/186d2583-9a2f-40bf-9d1e-49bc0896e626)


![image](https://github.com/user-attachments/assets/5c29ed37-0a07-44e0-a749-f0d0db770d51)



Uudelleen käynnistin apachen.
’sudo systemctl restart apache2’
Seuraavaksi yritin tehdä palomuurin reiän portille 443, mutta komentoa ’sudo ufw allow 443/tcp’ ei tunnistettu. Tästä teimme johtopäätöksen, ettei koko palomuuria ollut asennettu virtuaalipalvelimelle. Olin asentanut sen Linuxille aiemmin, mutta en ollut sitä huomannut erikseen virtuaalipalvelimelle asenttaa.
Joten pikimmiten asensin ’sudo apt-get install uwf’ palomuurin myös virtuaalipalvelimelleni.
’sudo ufw enable’ otettiin palomuuri käyttöön


Tein saman tien reiät palomuurille, http sekä HTTPS porteille.


’sudo ufw allow 22/tcp’ =palomuuri


’sudo ufw allow 80/tcp’ = HTTP


’sudo ufw allow 443/tcp’ = HTTPS


Nyt olin saanut palomuurin kuntoon, ja tehtyä reiät tarvittaville porteille, jotta verkkosivu toimisi kuten pitää.
Kokeilin selaimessa https://maariahakanpaa.com




![image](https://github.com/user-attachments/assets/b5aa0bf3-3d61-4961-9120-c886d98b62f7)




Sivu toimii, ja enkryptaus on nyt myös päällä.


## b)	A-Rating. Testaa oma sivusi TLS jollain yleisellä laadunvarmistustyökalulla, esim. SSLLabs


## 26.2.2025 14:05


Siirryin SSLLABS verkkosivuille (https://www.ssllabs.com/ssltest/), johon syötettiin oman verkkosivun osoite.




![image](https://github.com/user-attachments/assets/d31d6cbb-4425-429d-afab-bf010880c593)



Laadunvarmistustyökalu latasi oman aikansa ennen kuin tulos oli valmis.
Tuloksena oli tämä.



![image](https://github.com/user-attachments/assets/10f8fe1f-f03c-4220-83ae-ec91d42c0bc9)


Yhteenveto kertoo, että sivustoni olevan turvallinen ja asteikolla A taso on erinomainen. 


![image](https://github.com/user-attachments/assets/f1b6e1e0-acbe-40fe-867c-42caf48bdf5e)



Sertifikaatti osiossa on kerrottu sertifikaatin olevan luotettu ja voimassa oleva.



![image](https://github.com/user-attachments/assets/0180aa04-e8c5-4372-8f7c-9b7c500de323)



Konfiguraatio näyttää mitkä protokollat ovat käytössä, ja sivustollani on TLS 1.3 sekä TLS 1.2.
Cipher Suites määrittää miten turvallinen yhteys luodaan TLS protokollissa.



![image](https://github.com/user-attachments/assets/94b18ffc-fbdc-4e63-b94b-39c2270e42d7)



Handshake simulation on testausmielessä tehty prosessi, jossa asiakas ja palvelin luovat turvallisen yhteyden ja sopivat miten tieto salataan ja miten varmistetaan viestinnän turvallisuus. Tässä tapauksessa yksi testaus oli epäonnistunut.



![image](https://github.com/user-attachments/assets/a6bf78fd-f713-4ce2-9d0c-c2c2981e5d7b)

![image](https://github.com/user-attachments/assets/f1cf6c8f-d8f7-4457-9e21-85125143135c)



# Lähteet


Let’s Encrypt. 26.6.2024. Hot It Works. https://letsencrypt.org/how-it-works/. Luettu: 26.2.2025


Lego. 29.11.2024. Obtain a certificate. Using an existing, eunning web server. https://go-acme.github.io/lego/usage/cli/obtain-a-certificate/index.html#using-an-existing-running-web-server. Luettu 26.2.2025


The Apache Software Foundation 2025: Apache HTTP Server Version 2.4 [Official] Documentation: SSL/TLS Strong Encryption: How-To: Basic Configuration Example. https://httpd.apache.org/docs/2.4/ssl/ssl_howto.html#configexample. Luettu 26.2.2025


Qualys. SSL Labs. https://www.ssllabs.com/ssltest/. Luettu: 26.2.2025


Github/ssllabs. 4.2.2020. SSL Server Rating Guide. https://github.com/ssllabs/research/wiki/SSL-Server-Rating-Guide. Luettu:26.2.2025


Tero Karvinen. Linux Palvelimet 2025 alkukevät. https://terokarvinen.com/linux-palvelimet/. Luettu: 26.2.2025


StackExchange. Interpreting SSLLabs Handshake simulation results. https://security.stackexchange.com/questions/206137/interpreting-ssllabs-handshake-simulation-results. Luettu: 26.2.2025

