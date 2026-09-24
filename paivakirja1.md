# Oppimispäiväkirja 1: Paikallinen git

## Johdanto

Tässä oppimispäiväkirjassa tarkastelen oppimistani Paikallinen Git -osion aikana. Käsittelen erityisesti tehtävissä kohtaamiani haasteita, helposti omaksuttuja aiheita sekä oppimista tukeneita menetelmiä. Lisäksi kuvaan, miten ratkaisin tehtävien aikana ilmenneitä ongelmia. Lopuksi kokoan yhteen osiossa käyttämäni Git-komennot ja niiden käyttötarkoitukset.

## Mikä oli vaikeaa?

Paikallisen Git -osion aikana hieman haastavaa oli ymmärtää ja muistaa Gitin työhakemistossa esiintyvät tiedostojen tilat, kuten Tracked, Untracked, Unmodified, Modified ja Staged, sekä niiden väliset erot. Erityisesti alkuvaiheessa tuntui vaikealta hahmottaa, missä vaiheessa tiedosto siirtyy tilasta toiseen ja mitä kukin tila käytännössä tarkoittaa versionhallinnan näkökulmasta.

Muutosten peruuttamista käsittelevässä osiossa oli aluksi haastavaa erottaa toisistaan komennot git reset, git restore ja git revert, sillä kaikki liittyvät tavalla tai toisella muutosten kumoamiseen. Vaikka komentojen käyttötarkoitukset ovat osittain samankaltaisia, niiden vaikutukset repositoryyn, indeksiin ja työhakemistoon eroavat toisistaan merkittävästi. Tämän vuoksi komentojen muistaminen ja oikeiden käyttötapojen hahmottaminen vaati hieman aikaa ja harjoittelua.

Erityisesti git revert vaikutti aluksi melko pelottavalta komennolta, koska se luo uuden commitin ja muuttaa samalla työtilan sisältöä. Komennon toimintaperiaate kuitenkin selkeytyi, kun ymmärsin, ettei se poista tai muuta aiempaa commit-historiaa. Sen sijaan git revert säilyttää projektin historian ennallaan ja luo uuden commitin, joka kumoaa valitun commitin tekemät muutokset. Tämän vuoksi komentoa voidaan käyttää turvallisesti myös tilanteissa, joissa muutokset on jo jaettu muille kehittäjille.

Paikallinen Git -osion haastavinta sisältöä olivat kuitenkin haarat (engl. branches). Osiossa esiteltiin lyhyesti Gitin toimintaperiaatteita, jotta haarautumisen logiikkaa olisi helpompi ymmärtää. Tässä yhteydessä käsiteltiin erilaisia viitteitä (references), joiden hahmottaminen osoittautui minulle osittain haastavaksi.

Erityisesti HEAD-viitteen ja haaraviitteiden merkitys jäi alkuvaiheessa epäselväksi. Vaikka opetusmateriaalissa kerrottiin niiden käytöstä, en täysin ymmärtänyt, miten Git-versionhallinta toimii näiden käsitteiden osalta taustalla. Minulle heräsi useita kysymyksiä: mitä HEAD-viite tarkalleen tarkoittaa, mitä haaraviitteet ovat, miten ne toimivat ja mikä niiden keskinäinen suhde on. Lisäksi jäin pohtimaan niiden roolia Gitin toiminnassa kokonaisuutena.

Osiossa esiteltiin myös käsite snapshot, jonka merkitys ei ensimmäisellä lukukerralla avautunut minulle täysin. Koin, että pelkkä tekstimuotoinen selitys ei riittänyt näiden käsitteiden ymmärtämiseen. 

Osiossa haastavinta olivat myös niin sanotut eriytyneet haarat, jossa eri haaroissa on toisistaan poikkeavia muutoksia. Tästä aiheutuu ongelmia haarojen yhdistämissä, kun joudutaan ratkaisemaan yhdistämiskonflikteja (eng. merge conflicts). Varsinkin yhtään monimutkaisissa projekteissa, jossa on useita kehittäjiä ja useita eri ristiriitaisia muutoksia keskenään, aiheutuu paljon työtä yhdistymistä aiheutuvien konfliktien ratkaisuun. Tässä oppimateriaalissa ja harjoitustehtävissä ei esitelty vaikeampia yhdistämiskonflikteja, kun kaikki kehityshaaran muutokset pystyi suoraan yhdistämään päähaaraan ilman konflikteja.

## Mikä oli helppoa?

Harjoituksessa 1 Gitin asentaminen, version tarkistaminen sekä peruskonfigurointi olivat minulle melko helppoja tehtäviä. Linux-käyttöjärjestelmän käyttäjänä olen tottunut asentamaan ohjelmistoja komentoriviltä, joten Gitin käyttöönotto sujui vaivattomasti. Myös Gitin asetusten määrittäminen oli suoraviivainen prosessi, sillä komentojen tarkoitus oli selkeä ja niiden käyttö oli hyvin dokumentoitu.

Harjoituksessa 2 käsitellyt Gitin peruskomennot ja niiden muodostama työskentelyprosessi tuntuivat myös melko helposti omaksuttavilta. Erityisesti tiedostojen lisääminen versionhallintaan `git add` -komennolla sekä muutosten tallentaminen `git commit` -komennolla olivat minulle ennestään tuttuja toimintoja. Tämän vuoksi versionhallinnan peruskäyttö ja muutosten tallentamisen työvaiheet olivat helppoja ymmärtää ja soveltaa käytännössä.

Harjoituksessa 4 haarojen kanssa työskentely tuntui yllättävän luontevalta, vaikka Gitin haaroihin liittyvät sisäiset toimintaperiaatteet olivatkin osittain haastavia ymmärtää. Tehtävän ohjeita seuraamalla haarojen luominen, niiden välillä vaihtaminen ja haarojen yhdistäminen onnistuivat ilman suurempia ongelmia. Haarojen käsittelyyn liittyvät komennot olivat mielestäni melko intuitiivisia: `git branch <haara>` luo uuden haaran, `git switch` mahdollistaa haarojen välillä siirtymisen ja `git merge` yhdistää muutokset toisesta haarasta nykyiseen haaraan. Käytännön harjoitusten myötä jäi myös hyvin mieleen, että ennen yhdistämistä on tärkeää siirtyä siihen haaraan, johon muutokset halutaan yhdistää. Tässä tehtävässä haarojen yhdistäminen onnistui kuitenkin ongelmitta, koska päähaaran ja kehityshaaran välillä ei ollut ristiriitaisia muutoksia, jotka olisivat aiheuttaneet yhdistämiskonflikteja.

## Mikä auttoi minua oppimaan?

Paikallisen Git -osion aikana oppimistani auttoi erityisesti käytännön harjoittelu ja komentojen kokeileminen itse. Aluksi tiedostojen eri tilojen, kuten Tracked, Untracked, Modified ja Staged, muistaminen tuntui haastavalta. Tilojen merkitys alkoi kuitenkin hahmottua paremmin sitä mukaa, kun käytin Git-komentoja käytännössä ja pystyin seuraamaan, miten tiedostojen tila muuttui eri toimintojen seurauksena.

Muutosten peruuttamiseen liittyvien komentojen (git reset, git restore ja git revert) ymmärtämisessä auttoi niiden vaikutusten vertaileminen keskenään. Kun tutkin esimerkkejä ja harjoittelin komentojen käyttöä käytännössä, niiden väliset erot alkoivat vähitellen selkeytyä. Erityisesti ymmärrys siitä, mitä osaa versionhallinnasta kukin komento muuttaa, helpotti komentojen käyttötarkoitusten muistamista.

git revert-komennon osalta oppimistani auttoi sen toimintaperiaatteen syvempi ymmärtäminen. Kun ymmärsin, ettei komento poista aiempaa commit-historiaa vaan luo uuden commitin, joka kumoaa aikaisemmat muutokset, komennon käyttö tuntui huomattavasti selkeämmältä ja turvallisemmalta.

Haaroihin (branches), viitteisiin (references) ja Gitin sisäiseen toimintalogiikkaan liittyvien käsitteiden oppimisessa suurin apu oli visuaalisista kaavioista ja diagrammeista. Pelkkien tekstimuotoisten selitysten avulla minun oli vaikea hahmottaa esimerkiksi HEAD-viitteen, haaraviitteiden ja snapshotien merkitystä sekä niiden välisiä suhteita. Visuaaliset esitykset auttoivat näkemään, miten Gitin versiohistoria rakentuu ja miten eri viitteet osoittavat committeihin. Tämän ansiosta kokonaiskuva Gitin toiminnasta alkoi hahmottua huomattavasti paremmin.

Yleisesti ottaen oppimistani edistivät eniten käytännön harjoitukset, komentojen kokeileminen itse sekä visuaaliset havainnollistukset. Ne auttoivat muuttamaan abstraktit käsitteet konkreettisemmiksi ja helpommin ymmärrettäviksi.


## Miten selvitin esteet?

Gitin muutosten peruuttamiseen liittyvien komentojen ymmärtäminen oli aluksi haastavaa. En esimerkiksi täysin hahmottanut, miten git revert toimii käytännössä. Selvitin asiaa lukemalla opetusmateriaalin huolellisemmin sekä kokeilemalla komentoa omassa työympäristössäni. Käytännön harjoittelun avulla ymmärsin vähitellen, että git revert ei poista aiempaa commit-historiaa, vaan luo uuden commitin, joka kumoaa aiemmat muutokset. Tämä auttoi minua hahmottamaan komennon toimintaperiaatteen ja käyttötarkoituksen huomattavasti paremmin.

Myös git reset- ja git restore -komentojen erot olivat aluksi epäselviä. Ratkaisin tämän kokeilemalla komentoja erilaisissa tilanteissa ja tarkastelemalla niiden vaikutuksia git status- ja git log -komennoilla. Käytännön testauksen avulla pystyin seuraamaan, miten komennot vaikuttavat työhakemistoon, staging-alueeseen ja commit-historiaan. Näin niiden käyttötarkoitukset sekä keskinäiset erot alkoivat vähitellen hahmottua.

HEAD-viitteeseen, haaraviitteisiin ja Gitin sisäiseen toimintalogiikkaan liittyvät käsitteet aiheuttivat minulle myös haasteita. Selvitin näitä esteitä palaamalla opetusmateriaaliin useampaan kertaan ja perehtymällä erityisesti visuaalisiin kaavioihin ja diagrammeihin. Ne auttoivat hahmottamaan, miten Gitin viitteet liittyvät committeihin ja miten versionhallinnan historia rakentuu.

Ymmärtämistäni tuki myös vertauskuvien käyttö. Esimerkiksi hahmotin HEAD-viitteen ikään kuin lukupäänä, joka osoittaa parhaillaan käytössä olevaan haaraan. Haaraviitteet puolestaan toimivat osoittimina committeihin eli projektin tallennettuihin tilannekuviin. Tällaiset mielikuvat helpottivat abstraktien käsitteiden ymmärtämistä ja auttoivat muodostamaan selkeämmän kokonaiskuvan Gitin toiminnasta.

Koska opetusmateriaalissa ja harjoitustehtävissä ei käsitelty monimutkaisia yhdistämiskonflikteja, niiden käytännön harjoittelu jäi melko vähäiseksi. Täydensin osaamistani tutustumalla aiheeseen itsenäisesti erityisesti YouTubesta löytyvien opetusvideoiden avulla, jotka havainnollistivat merge-konfliktien syntymistä ja ratkaisemista. Ymmärsin myös, että konfliktien ratkaiseminen on taito, joka kehittyy ennen kaikkea käytännön kokemuksen kautta, etenkin useamman kehittäjän yhteisissä projekteissa. Lisäksi nykyaikaiset koodieditorit tarjoavat työkaluja konfliktien hallintaan, mutta usein tehokkain tapa ratkaista haastavat konfliktit on käydä muutokset läpi yhdessä tiimin kanssa ja yhdistää ne tarvittaessa manuaalisesti editorissa.



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
| git add <tiedosto> | Yksittäisen tiedoston lisääminen versionhallintaan |
| git add . | Kaikkien tiedostojen lisääminen versionhallintaan |
| git commit | Staging-muutosten tallentaminen versionhallintaan |
| git commit -m "<viesti>" | Staging-muutosten tallentaminen versionhallintaan annetulla viestillä. |
| git rm <tiedosto> | Tiedoston poistaminen versionhallinnasta ja hakemistosta. |
| git mv <vanha> <uusi> | Tiedoston nimeäminen tai siirtäminen versionhallinnassa |
| git log | Näyttää commit-talletusten historian |
| git log --stat | Näyttää commit-historian lyhyillä yhteenvedoilla talletusten muutoksista |
| git tag <tunniste> | Lisää tunnisteen viimeisempään committiin |
| git reset | Peruuta lisäys versionhallinnan tallennuksesta |
| git restore | Palauta tiedosto aikaisempaan versionhallinnassa olevaan versioon |
| git revert | Peruuta parametrina annetun versionhallinnan talletus kokonaan, tekemällä ns. "anti-talletus committin" |
| git branch <haara> | Uuden annetun haaran luominen git-versionhallintaan |
| git switch <haara> | Aktiivisen haaran vaihtaminen annettuun haaraan |
| git switch -c <haara> | Uuden haaran luominen ja siihen vaihtaminen samalla komennolla |
| git merge <haara> | Nykyisen työhaaran (esim. master) yhdistäminen annettuun haaraan |
| git merge --no-ff <haara> | Yhdistä annettuun haaraan, siten että se jää versionhallinnan historiaan ilman pikakelausta (no fast forward)  |
| git log --graph --all --oneline | Näytä git historia, johon kuuluvat koko historia yksirivisinä ja haarat graafisesti esitettyinä |

