---
layout: page
title: Viikko 7
inheader: no
permalink: /tehtavat7/
---

## Viikko 7

### Typoja tai epäselvyyksiä tehtävissä?

Tee [korjausehdotus](/osa0#typoja-materiaalissa) editoimalla [tätä](https://github.com/ohjelmistotuotanto-hy-avoin/ohjelmistotuotanto-hy-avoin.github.io/blob/master/tehtavat7.md) tiedostoa GitHubissa.

### Tehtävien palauttaminen

Tehtävät palautetaan GitHubiin, sekä merkitsemällä tehdyt tehtävät palautussovellukseen <https://study.cs.helsinki.fi/stats/courses/ohtu-avoin-2020>

Katso tarkempi ohje palautusrepositorioita koskien [täältä](/tehtavat1#teht%C3%A4vien-palautusrepositoriot).

### 1. git: stash [versionhallinta]

_tehtävien 1 ja 2 ei tarvitse näkyä palautuksessa, riittää kun teet tehtävät_

Lue <https://git-scm.com/book/en/v2/Git-Tools-Stashing-and-Cleaning> kohtaan _Creative stashing_ asti.

Oletetaan että olet repositoriossa, jossa on ainakin kaksi branchia: master ja joku toinen (kutsutaan sitä tässä nimellä __toinen__).

* ollessasi master-branchissa tee branchissa oleviin tiedostoihin muutoksia, joita lisäät staging-alueelle ja joitain muutoksia joita et vielä "äddää", komennon _git status_ tuloksen tulee näyttää siis suunilleen seuraavalta

```
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	new file:   README.md
    modified:   src/main/java/Main.java

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   src/main/java/Olutvarasto.java              
```
 
* pomosi käskee sinua välittömästi tekemään pari muutosta branchiin __toinen__. Et kuitenkaan halua vielä comittoida masterissa olevia muutoksia
* jos siirryt branchiin __toinen__ tekemättä comittia, tulee hirveä sotku, sillä muutokset pysyvät muutoksina toisessakin branchissa
* **git stash** pelastaa tästä tilanteesta, eli stashaa masterissa olevat muutoset
  * kokeile ennen ja jälkeen stash-komennon komentoa <code>git status</code>
* siirry branchiin toinen, tee sinne joku muutos jonka committaat
* palaa jälleen masteriin
* palauta stashatyt muutokset komennolla <code>git stash apply</code>
  * varmista että muutokset palasivat
  * kuten huomaat, staging-alueelle jo lisätty muutos ei palaa staging-alueelle, vaan joudut lisäämään sen uudelleen
  * jos edellisessä komento olisi annettu muodossa <code>git stash apply --index</code>, olisi tilanne palautunut täysin ennalleen

### 2. git: branchin "siirtäminen" [versionhallinta]

_tehtävien 1 ja 2 ei tarvitse näkyä palautuksessa, riittää kun teet tehtävät_

* tee repoosi branchi nimeltä haara ja tee masteriin ja haaraan committeja siten että saat aikaan seuraavankaltaisen tilanteen:

<pre>
    ____master
__/
  \_____haara
</pre>

* eli sekä master että haara ovat edenneet muutamien commitien verran haarautumisen tapahduttua
  * huom: komennolla <code>gitk --all</code> näet kaikki haarat, kokeile!
* yhtäkkiä huomaat, että master:iin tekemäsi asiat eivät olekaan kovin hyviä ja haara:ssa on paljon parempaa tavaraa, haluaisitkin että haara:sta tulisi uusi master
* tämä onnistuu kun menet masteriin ja annat komennon <code>git reset --hard haara</code>
  * varmista että komento toimii oikein
  * vanhan master-haarankaan tavarat eivät katoa mihinkään, jos niihin jostain syystä vielä halutaan palata
  * vanhaan committiin palaaminen onnistuu, jos commitin id on tiedossa -- jos ei, on olemassa [muutamia keinoja](http://stackoverflow.com/questions/4786972/list-of-all-git-commits) sen selvittämiseksi

### 3. ja 4. (kahden rastin tehtävä) KPS yksin- ja kaksinpeli

[Kurssirepositorion](https://github.com/ohjelmistotuotanto-hy/syksy2019) hakemistosta _koodi/viikko7/KiviPaperiSakset_ löytyy tutun pelin tietokoneversio. 

* ohjelmassa on kolme pelimoodia: ihminen vs. ihminen, ihminen vs. yksinkertainen tekoäly ja ihminen vs. monimutkainen tekoäly
* koodi sisältää runsaat määrät copy pastea, muutenkaan oliosuunnittelun periaatteet eivät ole vielä alkuperäisellä ohjelmoijalla olleet hallussa
* poista koodista kaikki toisteisuus ja tee siitä rakenteellisesti materiaalin [osan 4](/osa4) hengessä oikeaoppinen
  * pelaa-metodi tulee toteuttaa [template-metodina](/osa4#suunnittelumalli-template-method-viikko-5)
  * sopivan peliolion (kaksinpeli, helppo yksinpeli, vaikea yksinpeli) luominen tulee toteuttaa staattisen tehdasmetodin avulla
  * pääohjelmalla ei saa olla riippuvuuksia konkreettisiin pelin toteuttaviin luokkiin

Jos teet tehtävän mielestäsi kaikkien tyylisääntöjen mukaan, merkkaa 2 rastia, jos ratkaisu ei ole kaikin osin tyylikäs, merkkaa yksi rasti.

### 5. Kurssipalaute

Anna kurssipalautetta Moodlessa. Voit antaa palautteen myös kokeen jälkeen. Rasti tähän tehtävään on lupaus että annat palautteen jossain vaiheessa.

### Tehtävien palautus

Pushaa kaikki tekemäsi tehtävät GitHubiin ja merkkaa tekemäsi tehtävät palautussovellukseen <https://study.cs.helsinki.fi/stats/courses/ohtu-avoin-2020>
