# Oppimispäiväkirja: Git projektissa

__Mitä hyötyä voisi olla versionhallinnasta, jos kehität projektia yksin?__

Versionhallinnasta on useita hyötyjä myös yhden kehittäjän projekteissa.

Versionhallinta mahdollistaa projektissa tehtyjen muutosten dokumentoinnin ja seurannan. Commit-historian avulla voidaan tarkastella, mitä projektissa on muutettu ja milloin muutokset on tehty.

Versionhallinnan avulla voidaan myös tarkastella projektin aikaisempia versioita ja tarvittaessa palauttaa tehtyjä muutoksia. Jos jokin muutos on aiheuttanut ongelmia, voidaan  muutoksia peruuttaa turvallisesti esim. `git restore` ja `git revert` -komennoilla.

Git-haarojen avulla projektin uusia ominaisuuksia ja erilaisia kehitysversioita voidaan puolestaan kehittää erillään toimivasta pääversiosta. Uusia muutoksia voidaan siis kokeilla ilman, että projektin toimiva pääversio vaarantuu.

Hyödyntämällä etärepositoriopalveluita, kuten Githubia, projekti voidaan lisäksi pitää varmuuskopioituna myös paikallisen koneen ulkopuolella. Tämä tuo lisäturvaa tilanteisiin, jossa paikalliselle repositoriolle tai tietokoneelle tapahtuu jotain.


__Mitä hyötyä voisi olla versionhallinnasta, jos projektissa on useita kehittäjiä?__

Usean kehittäjän projekteissa versionhallinta tarjoaa pitkälti samoja hyötyjä kuin yhden kehittäjän projekteissa, mutta sen merkitys korostuu erityisesti yhteistyössa ja muutosten hallinnassa.

Ensisijaisesti se mahdollistaa usean kehittäjän työskentelemisen samaan projektin parissa samanaikaisesti. Git-aarojen avulla jokainen kehittäjä voi työstää omaa ominaisuuttaan erillään muista ilman, että keskeneräiset muutokset vaikuttavat suoraan muiden työskentelyyn tai projektin päähaaraan.

Versionhallinnan avulla muutokset voidaan jakaa yhteisen etärepositorion kautta ja yhdistää hallitusti yhteisiin kehitys- ja päähaaroihin. Näin eri kehittäjien tekemät muutokset saadaan osaksi samaa projektia hallitulla tavalla.

Yhdistämispyynnöt (Pull requests) mahdollistavat puolestaan taas muutosten tarkistamisen, kommentoinnin ja hyväksymisen ennen niiden yhdistämämistä yhteiseen päähaaraan. Tämä helpottaa yhteistyötä ja auttaa havaitsemaan mahdollisia ongelmia ennen muutosten yhdistämistä.

Aivan kuten yhden kehittäjän projektissa, versionhallinta ylläpitää myös git historiaa. Sen avulla tiimin jäsenet voivat seurata yhdessä, mitä muutoksia projektiin on tehty, kuka muutokset on tehnyt ja miten projekti on kehittynyt.

__Miten järjestäisit projektitiimin versionhallinnan 3-4 hengen ohjelmistoprojektikurssilla? Laadi tiimiläisille lyhyt ohje, miten projektissa toimitaan.__

Antaisin ohjelmistoprojektin tiimille seuraavat ohjeet:

1. Projektista luodaan yhteinen Github-repositorio ja varmistetaan että kaikilla tiimin jäsenilla on siihen käyttöoikeudet.
2. Kloonaa yhteinen repositorio omalle tietokoneellesi ennen työskentelyn aloittamista.
3. Käytä *master*-haaraa projektin vakaalle versiolle ja käytä yhteistä *develop* kehityshaaraa aktiivista kehitystyötä varten. Älä tee uusia ominaisuuksia suoraan *master*-haaraan.
4. Päivitä paikallinen *develop*-haara ennen uuden ominaisuuden aloittamista hakemalla uusimmat muutokset etärepositoriosta.
5. Luo jokaiselle uudelle ominaisuudelle oma haara päivitetystä *develop*-haarasta. Nimeät ominaisuushaarat kuvaavasti esim. *feature-login*.
6. Tee muutokset omassa paikallisessa ominaisuushaarassasi, ja tallenna ne säännöllisesti pieninä, selkeinä committeina. Kirjoita jokaiselle commitille lyhyt, alle 50 merkin otsikko, joka kuvaa tehtyä muutosta. Lisää tarvittaessa otsikon alle tarkempi kuvaus tehdyistä muutoksista.
7. Kun haluat jakaa tehdyt muutokset muun tiimin kanssa työnnä ominaisuushaarasi Githubiin.
8. Luo valmiista ominaisuudesta yhdistämispyyntö (Pull request) omasta haarastasi *develop* haaraan.
9. Pyydä tiimisi jäseniä tarkistamaan tehdyt muutokset. Korjaa yhdessä mahdolliset ongelmat ja yhdistämiskonfliktit ennen yhdistämispyynnön hyväksymistä.
10. Yhdistä hyväksytyt muutokset *develop*-haaraan ja poista sen jälkeen valmis ominaisuushaara, kun sitä ei enää tarvita.
11. Yhdistä testattu *develop*-haara *master*-päähaaraan, kun projektista valmistuu vakaa versio.


__Kommenttini opintojaksosta, esim. sisällöstä, materiaalista, työmäärästä, hyödyllisyydestä, työmäärästä. Mitä toivoisit olevan enemmän, mitä vähemmän?__

Mielestäni kurssin sisältö ja erityisesti sen oppimmateriaali oli kokonaisuudesssaaan laadukkaasti tuotettua ja monipuolista. Materiaali oli helposti lähestyttävää ja selkeästi kirjoitettua ja se tuki erinomaisesti oppimista. Erityisesti materiaalissa esitetyt diagrammit, kuvaukset ja komentoesimerkit auttoivat hahmottamaan Gitin toimintaa ja ymmärtämään sen käyttöä käytännössä.

Myös harjoitustehtävät olivat hyvin suunniteltua ja kävivät monipuolisesti läpi Gitin keskeisiä komentoja ja toimintaperiaatteita. Tehtävät auttoivat vahvistamaan opittuja asioita sekä sisäistämään Gitin käyttöä, siten että se vastasi hyvin hyödyntämistä oikeassa työympäristössä.

Kaiken kaikkiaan koin, että opetusmateriaalissa käsitellyt Gitin perusteet sekä harjoitustehtävät olivat erittäin hyödyllisiä ja tukivat hyvin oppimistani. En löytänyt opestusmateriaalista mitään erityistä parannettavaa.

Työmäärältään kurssi oli mielestäni juuri sopiva suhteessa sen 2 opintopisteen laajuuteen. Myös harjoitustehtävien määrä ja laajuus olivat sopivia -- tehtäviä ei ollut liikaa, vaan ne riittivät asioiden kertaamiseen ja opittujen asioiden sisäistämiseen.

Jos pitäisi toivoa mitä kurssissa voisi olla enemmän, niin toivoisin enemmän teoriaa ja tehtäviä useamman henkilön projektin versionhallinnasta työskentelystä. Erityisesti yhdistämiskonfliktien ratkaisemiseen voisi olla enemmän tehtäviä, sillä uskon niiden aiheuttavan helposti eniten haasteita Gitin käytössä oikeassa työympäristössä. Harjoitus 6:ssa oli jo hieman simuloitu yhdistämiskonfliktien ratkaisemista, mutta mielestäni aihetta olisi voinut käsitellä vielä laajemmin. Esimerkiksi konfliktien tarkoituksellista luomista ja järjestelmällistä ratkaisemista olisi voinut olla enemmän.

Lisäksi Gitin eri tapoja yhdistää ja siistiä haarojen historiaa, kuten git rebase ja git squash, olisi voitu käsitellä tarkemmin. Toisaalta Gitissä on paljon komentoja ja ominaisuuksia, joten kaikkia ei ole tarkoituksenmukaista käydä läpi Git-versionhallinnan perusteet -kurssilla.

Erityisesti mitään vähennettävää en keksi kurssilla.

Kaiken kaikkiaan antaisin kurssille arvosanaksi erinomaisen. Erityisesti kurssin hyödyllisyys ja laadukas opetusmateriaali tekivät siitä erittäin onnistuneen kokonaisuuden.
