# Oppimispäiväkirja: Hajautettu git

Tässä oppimispäiväkirjassa käsittelen Hajautettu Git -osion tehtäviä ja niissä oppimiani asioita. Keskityn erityisesti GitHubin ja etärepositorion käyttöön, haarojen hallintaan sekä Gitin ja GitHubin väliseen työskentelyyn.

## 1. Mikä osion tehtävissä oli vaikeaa?

Harjoituksen 5 tehtävät eivät itsessään tuottaneet vaikeuksia, sillä niissä käytetyt Git-komennot olivat pääasiassa samoja haarojen hallintaan liittyviä komentoja, joita käsiteltiin Paikallinen Git -osiossa. Tällä kertaa uutena asiana oli kuitenkin se, että pelkän paikallisen Git-repositorion hallinnan lisäksi mukaan tuli myös GitHub-palvelussa sijaitsevan etärepositorion hallinta.

Harjoituksen 5 haasteet liittyivätkin GitHub-profiiliin tunnistautumiseen. Koska en ollut määrittänyt etärepositorion käyttöoikeuksia työympäristössäni, en pystynyt siirtämään paikallisesti tehtyjä muutoksia https://github.com/ osoitteessa sijaitsevaan GitHub-repositorioon.

Ongelmaan ei löytynyt ratkaisua pelkästään Git-versionhallintakurssin opintomateriaalista, joten jouduin perehtymään aiheeseen tarkemmin verkosta löytyvän dokumentaation avulla. Tämän avulla pystyin ratkaisemaan ongelman ja suorittamaan harjoituksen 5 tehtävät loppuun.

Joskus oli vaikea muistaa, että `git remote add origin`- ja `git push -u origin master` -komennoissa origin viittaa nimettyyn etärepositorioon. Tämä aiheutti välillä hieman hämmennystä.

## 2. Mikä osion tehtävissä oli helppoa?

 Mielestäni harjoituksen 5 tehtävät olivat kokonaisuudessaan melko helppoja sen jälkeen, kun sain ratkaistua GitHub-tunnistautumiseen liittyvät ongelmat.

 - Uuden repositorion luominen GitHub-profiiliin onnistui helposti verkkokäyttöliittymän kautta.
- Etärepositorion määrittäminen paikalliselle Git-hakemistolle komennolla `git remote add origin <url>` oli yksinkertaista.
- Paikallisen haaran vieminen etärepositorioon `git push` -komennolla ei tuottanut vaikeuksia.
- Haarojen ja tiedostojen hallintaan liittyvät komennot olivat jo entuudestaan tuttuja **Paikallinen Git** -osiosta. Esimerkiksi uuden `new-feat`-haaran luominen komennolla `git switch -c new-feat` sekä muutosten lisääminen ja tallentaminen `git add`\- ja `git commit` -komennoilla olivat helppoja suorittaa.
- Uuden tiedoston luominen GitHub-palvelun verkkokäyttöliittymässä oli helppoa ja selkeää.
- Muutosten hakeminen etärepositoriosta `git fetch` -komennolla oli mielestäni helppoa ja suoraviivaista.
- Eri haarojen yhdistäminen oli helppoa ja tuttua, kunhan muisti ensin siirtyä yhdistettävään haaraan `git switch` -komennolla ja sen jälkeen yhdistää toinen haara `git merge <haara>` -komennolla. Etärepositorion haaroja yhdistettäessä piti lisäksi muistaa, että esimerkiksi `origin/new-feat` viittaa `origin`-etärepositorion `new-feat`-haaraan. Haarojen yhdistämistä helpotti se, ettei tehtävissä tarvinnut ratkaista merge-konflikteja, vaan muutokset saatiin yhdistettyä suoraan.



## 3. Mikä auttoi minua oppimaan?


 **Hajautettu Git** -osion oppimista tukivat pitkälti samat käytänteet kuin **Paikallinen Git** -osiossa.

 - Kertasin ensin **Paikallinen Git** -osion teoriaa ja tutustuin sen jälkeen **Hajautettu Git** -osion opetusmateriaaliin. Tämä auttoi vahvistamaan teoriapohjaani Gitin toimintaperiaatteista. Erityisesti perehdyin käytettäviin komentoihin ja niiden esimerkkeihin.
- Paras tapa oppia oli kuitenkin suorittaa Git-komennot itse omassa työympäristössäni. Käytännön tekeminen auttoi ymmärtämään, miten komennot vaikuttavat repositorion sisältöön ja historiaan.
- Oppimistani tukivat myös säännöllinen `git status`\- ja `git log`-komentojen käyttö tehtävien aikana. Näiden avulla pystyin konkreettisesti seuraamaan tekemiäni muutoksia ja Git-versionhallinnan tilaa.
- Myös GitHubin selkeä verkkokäyttöliittymä tuki oppimistani, sillä sen avulla pystyin tarkastelemaan versionhallinnan tilaa ja muutoksia visuaalisesti.
- GitHubin autentikointiin liittyvien ongelmien ratkaisemista helpotti GitHubin oma ja selkeä dokumentaatio.

## 4. Miten selvitin esteet, jotka vaikuttivat tehtävän suorittamiseen?

Harjoituksen 5 tehtävien suorittamista vaikeuttivat GitHub-palveluun liittyvät autentikointiongelmat. Minulla ei ollut työympäristössäni tarvittavia käyttöoikeuksia paikallisessa Git-repositoriossa tehtyjen muutosten pushaamiseen GitHubissa sijaitsevaan etärepositorioon. Löysin ongelmaan ratkaisun perehtymällä GitHubin omaan dokumentaatioon, josta sain lisätietoa GitHubin autentikoinnista.

Ensimmäisenä ratkaisuna loin uuden *GitHub Access Tokenin* GitHub-käyttäjäprofiilini asetuksista ja annoin sille luku- ja kirjoitusoikeudet harjoituksessa käytettyyn repositorioon. Tämän jälkeen pystyin pushaamaan paikalliset muutokseni HTTPS-yhteyden kautta GitHub-repositorioon. Kun Git kysyi salasanaa, käytin salasanan sijasta luomaani autentikointitokenia.

Ratkaisu ei kuitenkaan tuntunut itselleni mielekkäältä, sillä jouduin syöttämään autentikointitokenin uudelleen lähes jokaisen push-komennon yhteydessä. GitHub muisti autentikoinnin vain rajallisen ajan, joten päätin etsiä ongelmaan toisen, käytännöllisemmän ratkaisun.

Päädyin lopulta hyödyntämään SSH-avaimia GitHubiin tunnistautumisessa. Tähän löytyi selkeät ohjeet GitHubin autentikointia käsittelevästä dokumentaatiosta.
Sain SSH-autentikoinnin toimimaan seuraavilla vaiheilla:


**1. SSH-avaimen luominen**

Ensimmäisenä loin koneellani uuden SSH-avaimen:

```
ssh-keygen -t ed25519 -C "teemu.tanninen@myy.haaga-helia.fi"
```

 Komennon suorittamisen jälkeen kotihakemistooni luotiin kaksi avainta:

 - Julkinen avain: `~/.ssh/id_ed25519.pub`
- Yksityinen avain: `~/.ssh/id_ed25519`

**2. SSH-agentin käynnistäminen**

 Seuraavaksi käynnistin SSH-agentin:

```
eval "$(ssh-agent -s)"
```

 Tämän jälkeen lisäsin luomani yksityisen avaimen SSH-agenttiin:

```
ssh-add ~/.ssh/id_ed25519
```

**3. Julkisen avaimen lisääminen GitHubiin**

 Kopioin julkisen SSH-avaimen leikepöydälle seuraavalla komennolla:

```
cat ~/.ssh/id_ed25519.pub | wl-copy
```

 Tämän jälkeen siirryin GitHub-profiilini asetuksiin ja lisäsin julkisen SSH-avaimeni GitHubin SSH-avainten hallintaan.

**4. Etärepositorion osoitteen muuttaminen**

 SSH-autentikoinnin käyttöönoton jälkeen minun piti vielä vaihtaa paikallisessa repositoriossa käytetty etärepositorion osoite HTTPS-muodosta SSH-muotoon.

 Alun perin etärepositorio oli määritetty HTTPS-osoitteella:

```
git remote add origin https://github.com/NikodemiusTKT/git-harjoittelua.git
```

 Vaihdoin osoitteen SSH-muotoon komennolla:

```
git remote set-url origin git@github.com:NikodemiusTKT/git-harjoittelua.git
```

Tämän jälkeen pystyin tekemään muutoksia GitHubin etärepositorioon ilman, että minun tarvitsi syöttää autentikointitokenia jokaisen push-komennon yhteydessä. SSH-avainten ansiosta yhteys voitiin muodostaa SSH:n kautta ilman jatkuvaa tokenin syöttämistä.

## Osiossa käyttämäni Git-komennot

| Komento | Kuvaus |
| --------| ------ |
| `git remote add origin <url>` | Lisää etärepositorion annetulla url-osoitteella ja antaa sille nimeksi `origin` |
| `git remote -v` | Listaa etärepositoriot ja niiden URL-osoitteet |
| `git push -u origin <haara>` | Vie paikallisen haaran etärepositorioon ja asettaa origin-etärepositorion sen oletukseksi. |
| `git push` | Vie paikalliset muutokset etärepositorioon |
| `git branch` | Listaa paikalliset haarat |
| `git switch -c <haara>`| Luo uuden haaran ja vaihtaa siihen |
| `git switch <haara>` | Vaihtaa annettuun haaraan |
| `git switch origin/new-feat` | Vaihtaa `origin`-etäreposition `new-feat` haaran. |
| `git add <tiedosto>` | Lisää tiedoston valmisteltuihin muutoksiin (staged) |
| `git commit -m <viesti>` | Tallentaa valmistellut muutokset versionhallintaan annetulla viestillä. |
| `git fetch` | Hae muutokset etärepositoriosta yhdistämättä niitä paikalliseen haaraan |
| `git merge <haara>` | Yhdistää annetun haaran nykyiseen työhaaraan |
| `git merge --no-ff <haara>` | Yhdistää annetun haaran nykyiseen työhaaraan ja säilyttää yhdistämisen historiassa |
| `git status` | Näyttää repon ja git työhakemiston nykyisen tilanteen |
| `git tag harjoitus5` | Lisää harjoitus5-tunnisteen nykyiseen tallenteeseen. |
| `git log --oneline --decorate --graph --all` | Näyttää tiivistetyn versionhallintahistorian ja haarojen rakenteen |


