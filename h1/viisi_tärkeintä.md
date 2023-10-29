# Viisi Tärkeintä 

Tehtävässä käytetään ![Tero Karvisen antamia komentoja ja oppimateriaalia](https://terokarvinen.com/2021/salt-run-command-locally/).

## pkg.installed

![img](./micro_inst.png)  

Tässä annetaan käsky Micro tekstieditorin lataamiseen.  
Voimme toki tehdä myös vastakkaisen käskyn ja poistaa Micro koneelta komennolla:  
(Näytän tämän tässä tehtävässä kerran koska sinällään efekti on täysin sama mutta, vastakkainen)

```sudo salt-call --local -l info state.single pkg.removed micro``` 

![img](./micro_rem.png)  

Huomaamme että tässä Saltti on poistanut Micron koneeltamme juuri niinkuin sitä on käsketty.

## file.managed/absent

![img](./file_managed.png)  

Tässä huomataan että luodaan tekstitiedosto jos se ei ole olemassa meidän määräämässä kansiossa. Vastaavasti file.absent poistaa tiedoston.

## service.running/dead

![img](./apa_true.png)  

Näemme että Apache2-palvelin on toiminnassa ja kokeillaan sammuttaa se käsin.  

![img](./apa_stopped.png)  

Huomaamme että se on alhaalla ja käsketään Saltti käynnistää se uudelleen.  

![img](./apa_restart.png)  

## user.present/absent

Luodaan käyttäjä nimeltä tero ja annetaan sille kenkää.  

![img](./tero_kick.png)

## cmd.run

![img](./echo_hell.png)  

Olkoon, antaa koneen echottaa Hello Worldia. Tätä voi toistaa ikuisesti ja aina on changed = 1, kyseessä ei ole idempotenssi tila. (Viisikko, JussiMol)

# Lähteet
Infra as Code 2023, Tero Karvinen
https://terokarvinen.com/2023/configuration-management-2023-autumn/

Run Salt Command Locally, Tero Karvinen
https://terokarvinen.com/2021/salt-run-command-locally/

Viisikko H1, JussiMol
https://github.com/JussiMol/Palvelinten-hallinta/blob/main/h1/Viisikko.md
