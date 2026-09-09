# Oppimispäiväkirja: Paikallinen git

__Mikä osion tehtävissä oli vaikeaa ja mikä helppoa? Mikä auttoi minua oppimaan? Miten selvitin esteet?__

**Mikä oli vaikeaa?**

- Aluksi on hieman vaikeaa erottaa git reset-, git restore- ja git revert-komennot toisistaan, koska kaikki liittyvät muutosten peruuttamiseen. Komentojen käyttötarkoitukset ja vaikutukset kuitenkin eroavat toisistaan, mikä tekee niiden muistamisesta haastavaa.

- git revert vaikuttaa aluksi melko pelottavalta komennolta, koska se tekee uuden commitin ja muuttaa samalla työtilan sisältöä. Komennon toiminta kuitenkin selkeytyy, kun ymmärtää, ettei se muuta tai poista aikaisempaa commit-historiaa. Sen sijaan git revert luo uuden commitin, jossa aikaisemmin tehdyt muutokset kumotaan.

**Mikä oli helppoa?**

* Gitin asentaminen, version tarkistaminen sekä Gitin peruskonfigurointi olivat helppoja tehtäviä.
* Myös Gitin peruskomennot ja niiden muodostama työskentelyprosessi tuntuivat melko selkeiltä. Erityisesti tiedostojen lisääminen versionhallintaan `git add` -komennolla ja muutosten tallentaminen `git commit` -komennolla oli helppo ymmärtää.

**Mikä auttoi minua oppimaan?**

* Oppimistani auttoi selkeä ja laadukas kurssimateriaali, joka sisälsi kattavat komentojen selitykset sekä käytännön käyttöesimerkkejä.
* Git-komentojen suorittaminen itse omassa työympäristössäni auttoi ymmärtämään niiden toimintaa paremmin ja sisäistämään opitut asiat käytännön kautta.
* `git status`- ja `git log` -komentojen käyttäminen muutosten tekemisen jälkeen auttoi hahmottamaan paremmin Git-repositorion senhetkisen tilanteen sekä ymmärtämään, miten tehdyt muutokset vaikuttavat työtilaan ja commit-historiaan.

**Miten selvitin esteet?**

En aluksi ymmärtänyt kunnolla, miten git revert -komento toimii. Selvitin asiaa lukemalla opetusmateriaalin tarkemmin ja kokeilemalla komentoa käytännössä omassa työympäristössäni. Käytännön kokeilujen avulla ymmärsin paremmin, miten git revert toimii ja miten se eroaa muiden muutosten peruuttamiseen käytettävien komentojen toiminnasta.

Myös git reset- ja git restore -komentojen käyttötarkoitukset olivat aluksi epäselviä. Selvitin niiden eroja kokeilemalla komentoja käytännössä ja tarkastelemalla niiden vaikutuksia git status- ja git log -komennoilla. Näin ymmärsin vähitellen, milloin kumpaakin komentoa käytetään ja miten ne vaikuttavat työtilaan, staging-alueeseen ja commit-historiaan.



## Osiossa käyttämäni Git-komennot

| Komento | Kuvaus |
| --------| ------ |
| git --version | git versionumeron tulostus |
| git config --global set user.name| Git:n käyttäjänimen asetus globaalisti |
| git config --global set user.email | Git:n Sähköpostiosoitteen asetus globaalisti |
| git config --global set core.editor | Git:ssä käytetyn tekstieditorin asetus. |
| git config list --global | Git:n globaalien asetusten tulostus |
| git init | Uuden git-repositorion alustaminen hakemistoon |
| git status | Repositorion nykyisen tilan tarkastaminen |
| git add hello.html | Yksittäisen tiedoston lisääminen versionhallintaan |
| git add . | Kaikkien tiedostojen lisääminen versionhallintaan |
| git commit -m "viesti" | Staging-muutosten tallentaminen versionhallintaan annetulla viestillä. |
| git rm test.txt | Tiedoston poistaminen versionhallinnasta ja hakemistosta. |
| git mv hello.html index.html | Tiedoston nimeäminen tai siirtäminen versionhallinnassa |
| git log | Näyttää commit-talletusten historian |
| git log --stat | Näyttää commit-historian lyhyillä yhteenvedoilla talletusten muutoksista |
| git tag harjoitus2 | Lisää tunnisteen viimeisempään committiin |
| git reset | Peruuta lisäys versionhallinnan tallennuksesta |
| git restore | Palauta tiedosto aikaisempaan versionhallinnassa olevaan versioon |
| git revert | Peruuta parametrina annetun versionhallinnan talletus kokonaan, tekemällä ns. "anti-talletus committin" |

