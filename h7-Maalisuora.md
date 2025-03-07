
# h7 Maalisuora


**Työskentely ympäristö**


**Laite:** Lenovo Ideapad 3

**Suoritin:** 11th Gen Intel(R) Core(TM) i5-1135G7 @ 2.40GHz 2.42 GHz

**Asennettu RAM:** 8,00 Gt (7,80 Gt käytettävissä)

**Järjestelmätyyppi:** 64-bittinen käyttöjärjestelmä, x64-suoritin

**Versio:** Windows 11 Home, 24H2

**Verkko:** WLAN

**Virtuaalikone:**


![image](https://github.com/user-attachments/assets/655063e8-b4cf-472e-93a8-5c0bf7344734)





# a) Kirjoita ja aja "Hei maailma" kolmella kielellä.



**6.3.2025 11:15**

  

Valitsin kieliksi pythonin, bashin ja javan. Java oli ainoa kieli joka oli itselleni ennestään tuttu näistä.

Aloitin tehtävän luomalla uuden kansion

’mkdir komennot’ johon lisäsin luomani uudet komennot eri kielillä.


  
## Python


  
![image](https://github.com/user-attachments/assets/2c8eae8f-c267-4a84-b044-a575d089d11e)



Komennolla ’chmod ugo+x heimaailma.py’ annoin käyttäjille execute oikeudet tiedostoon.


Avasin nano tekstieditorin, jotta pääsin tekemään tiedostolle sisällön ’nano heimaailma.py’



Aloitin luomalla python tiedoston nimellä heimaailma, annoin käyttäjille execute oikeudet tiedostoon, sekä avasin nano tekstieditorin.




![image](https://github.com/user-attachments/assets/ef11eb06-e022-47aa-88b4-b242d7727b09)



Sitten kokeilin komennon toimintaa.




![image](https://github.com/user-attachments/assets/bfff145f-243f-43b2-9958-456a8cf98d53)



## Bash


Seuraavaksi tein komennon bashilla ’touch script.sh’ jolloin tiedosto luotiin ja ’nano script.sh’ , jolloin pääsin tekstieditoriin luomaan varsinaisen komennon.




![image](https://github.com/user-attachments/assets/307b8f52-c03b-4207-a75b-bcd8c5008717)



![image](https://github.com/user-attachments/assets/fb308a36-b509-4b02-8928-480fb1379510)



## Java


Viimeisen komennon tein javalla, loin tiedoston ’touch Heimaailma.java’ sitten avasin tekstieditorin (nano) 





![image](https://github.com/user-attachments/assets/2d65192c-86e0-4f04-8287-26892ab173dc)



Yritettyäni suorittaa komentoa tajusin kuitenkin, ettei javaa ollut vielä edes asennettu.



![image](https://github.com/user-attachments/assets/9ccf76c7-e184-4b86-ab4a-a4dabdf1c0bb)




Joten asensin seuraavaksi javan JDK paketin. ’ apt-get install default-jdk’


Kokeilin uudestaan komentoja.


 
![image](https://github.com/user-attachments/assets/44163767-d002-4a61-b853-ee4e133c14f0)




Nyt komento toimi odotusten mukaan.



![image](https://github.com/user-attachments/assets/48c158cc-8e2e-42ff-9897-40828d44f781)




# c) Laita Linuxiin uusi, itse tekemäsi komento niin, että kaikki käyttäjät voivat ajaa sitä.



**6.3.2025 13:10**



Loin uuden komennon 


![image](https://github.com/user-attachments/assets/cc862733-f4b1-4c4c-86a9-14970d09260d)



Lisäsin sinne neljä erilaista komentoa.


![image](https://github.com/user-attachments/assets/7912e41e-0bec-4491-8ab0-6618cdbd1cdb)



Seuraavaksi annoin käyttöoikeudet suorittaa (execute) komentoa.


![image](https://github.com/user-attachments/assets/13ed740e-673e-426b-9e5a-3c4c18366c57)




Kopioin tiedoston toiseen kansioon, josta kaikki käyttäjät voivat käyttää komentoa.




![image](https://github.com/user-attachments/assets/aff87038-72af-4b9d-a29e-aec778fe8fbf)




Kokeilin omalla käyttäjälläni, että komento toimii.





![image](https://github.com/user-attachments/assets/587f9b6d-b2a6-4852-ac8a-bd04e7139743)



Ja se toimikin odotetulla tavalla.



Olin aikaisemmin tehnyt toisen käyttäjän Linuxille (’sudo adduser lila’), jotta pääsisin myös sen avulla testaamaan, toimiiko komento.



![image](https://github.com/user-attachments/assets/fa2d3edb-b8b4-46bd-8247-969eb0092aed)




Komento toimii myös toisella käyttäjällä.



# d) Ratkaise vanha arvioitava laboratorioharjoitus soveltuvin osin.


**6.3.2025 14:00**


Valitsin laboratorioharjoitukseksi Final Lab for Linux Palvelimet 2024 Spring, jonka löysin Tero Karvisen sivuilta (https://terokarvinen.com/2024/arvioitava-laboratorioharjoitus-2024-linux-palvelimet/)




## d) Tee kaikkien käyttäjien käyttöön komento 'howdy'
-	Tulosta haluamaasi ajankohtaista tietoa, esim päivämäärä, koneen osoite tms
-	Pelkkä "hei maailma" ei riitä
-	Komennon tulee toimia kaikilla käyttäjillä työhakemistosta riippumatta



Aloitin luomalla micro tiedoston:



![image](https://github.com/user-attachments/assets/c1e80a30-83ab-4ac3-8798-8eedfa05299e)




Lisäsin sinne komennot joka näyttää päiväyksen, koneen päällä olo ajan sekä käyttäjän joka sillä hetkellä on kirjautuneena.



![image](https://github.com/user-attachments/assets/a33ce0f6-458c-4574-b917-c18f80396f53)



Seuraavaksi laitoin käyttäjille execute oikeudet 



![image](https://github.com/user-attachments/assets/4f06a745-30ba-4073-9a8f-70e252976bd1)



Testasin komennon toimivuuden.




![image](https://github.com/user-attachments/assets/b76d4e31-6653-4023-ad1e-f70c47a76239)




Kopioin tiedoston toiseen kansioon, jotta kaikilla käyttäjillä on siihen pääsy.



![image](https://github.com/user-attachments/assets/31042961-4190-4f3c-93b3-2744577ec813)



Komento toimii nyt pelkällä ’howdy’ komennolla.




![image](https://github.com/user-attachments/assets/d4ad4b24-4449-4c40-b4fe-859670588472)




Kokeilin sitä vielä toisella käyttäjällä:



![image](https://github.com/user-attachments/assets/47a55cd8-420b-4e35-a5e1-37ecb16d0dfa)



## e) Etusivu uusiksi



-	Asenna Apache-weppipalvelin
-	Tee yrityksellemme "AI Kakone" kotisivu
-	Kotisivu tulee näkyä koneesi IP-osoitteella suoraan etusivulla
-	Sivua pitää päästä muokkaamaan normaalin käyttäjän oikeuksin (ilman sudoa). Liitä raporttiisi listaus tarvittavien tiedostojen ja kansioiden oikeuksista.


Apache weppi-palvelimen olin asentanut jo aikaisemmin, joten siirryin suoraan seuraavaan kohtaan.



Tein ensin etusivulle Default tekstin.


![image](https://github.com/user-attachments/assets/7487d9fa-bca1-45e9-a277-808db9d81ac8)



Käynnistin apachen uudelleen ’sudo systemctl restart apache2’



Muokkasin .conf tiedostoa




![image](https://github.com/user-attachments/assets/b4977ae3-544f-4b9e-a2b4-e792f013d065)




![image](https://github.com/user-attachments/assets/e81279fe-32d4-4f23-9cd0-4fd4c1eec5cf)




Otin sivun käyttöön ja uudelleen käynnistin apachen.



![image](https://github.com/user-attachments/assets/2b3f0657-9db5-46ae-9d58-65a353c7bc42)



Kävin luomassa public_sites kansioon aikakone.com kansion ja sen alle index.html tiedoston.




![image](https://github.com/user-attachments/assets/87c921e5-fecc-403a-b716-f51a1e9d4e35)




Sitten käynnistin apachen uudelleen.



Kävin selaimen puolella tarkistamassa näkyykö sivu.



![image](https://github.com/user-attachments/assets/b8eefbbe-9f90-4f83-ad3b-bb01f5640440)




Sivu näkyy oikein.



Tarkistin vielä että tiedostoa voi muokata tavallisena käyttäjänä.



![image](https://github.com/user-attachments/assets/5a16affe-ae06-47b5-a9b0-a6613f15dbd8)



![image](https://github.com/user-attachments/assets/58ee91da-858f-4dbe-8950-1cd9908875c6)




# e) Asenna itsellesi tyhjä virtuaalikone arvioitavaa labraa varten.



**7.3.2025 14:10**



Asensin uuden virtuaalikoneen (Debian 12-Bookworm amd64) ja tein siihen vain sallitut päivitykset.




![image](https://github.com/user-attachments/assets/a69399f8-affb-4ab8-8f24-756e90f5595e)



# Lähteet


GeeksforGeeks. 13.3.2024. How to Create a Shell Script in linux. https://www.geeksforgeeks.org/how-to-create-a-shell-script-in-linux/


Tero Karvinen. 4.12.2007. Shell Scripting. https://terokarvinen.com/2007/12/04/shell-scripting-4/


Tero Karvinen. 27.9.2018. Hello World Python3, Bash, C, C++, Go, Lua, Ruby, Java – Programming Languages on Ubuntu 18.04. https://terokarvinen.com/2018/hello-python3-bash-c-c-go-lua-ruby-java-programming-languages-on-ubuntu-18-04/


Tero Karvinen. Linux palvelimet 2025 alkukevät. https://terokarvinen.com/linux-palvelimet/#h7-maalisuora


Debian wiki. Java. https://wiki.debian.org/Java


I/O FLOOD. 28.12.2023. Switching Users in Linux: The SU Command Explained. https://ioflood.com/blog/su-linux-command/


Tero Karvinen. Final Lab for Linux Palvelimet 2024 Spring.  https://terokarvinen.com/2024/arvioitava-laboratorioharjoitus-2024-linux-palvelimet/


Tero Karvinen. Install Debian on Virtualbox - Updated 2024. https://terokarvinen.com/2021/install-debian-on-virtualbox/


GitHub/dwsion. Linux_palvelimet/h7.md. https://github.com/dwsion/Linux_palvelimet/blob/main/h7.md


GitHub/LeeviRaussi. linux-palvelimet/h7_Maalisuora.md. https://github.com/LeeviRaussi/linux-palvelimet/blob/main/h7_Maalisuora.md


GitHub/koskinene. linux-course/h7.md. https://github.com/koskinene/linux-course/blob/main/h7.md

  
