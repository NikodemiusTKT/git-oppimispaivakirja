# Oppimispäiväkirja: Paikallinen git

__Mikä osion tehtävissä oli vaikeaa ja mikä helppoa? Mikä auttoi minua oppimaan? Miten selvitin esteet?__

**Mikä oli vaikeaa?**

**Mikä oli helppoa?**

- Helppoa olivat git:n asennus, git versiontulostus ja gitin konfigurointi.
- Helpolta tuntui git:n peruskomennot ja prosessi, jossa tiedostoja lisätään versionhallintaan `git add` komennolla ja sitten tallennetaan lopullisesti `git commit` komennolla. 

**Mikä auttoi minua oppimaan?**

- Oppimista auttoivat laadukas selkeä kurssin oppimateriaali, johon kuuluivat myös kattavat komentojen selitykset ja käyttöesimerkit.
- Myös komentojen suorittaminen konkreettisesti itse omassa työympäristössä auttoivat asioiden sisäistämisessä.

**Miten selvitin esteet?**



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

