# h1-Kybertappoketju

x)Darknet Diaries jakso 156 Kill list:
- Chris Monteiro tutkii Dark Webbiä ja etsii, mikä on totta ja mikä tarua. Hän tekee blogin sivusta, jossa voit palkata palkkamurhaajan. Chris saa oikeudet, jossa hän näkee muitten käyttäjien viestit ja huomaa että niitä on monia satoja, joissa on vaihdettu rahaa (bitcoineja) jotta joku henkilö murhattaisiin. 
- Sivusto on täysin tekaistu ja oikeita palkkamurhaajia ei ole, mutta monet ihmiset, jotka sivulle tekee tilauksen ovat jo niin uponneita murhan suunnitteluun, että saattavat tehdä sen itse. Jaksossa mainitaan tapaus, jossa Yhdysvalloissa FBI on yhteydessä naiseen, joka on vaarassa, jälkikäteen huomataan, että hänen miehensä on tehnyt tilauksen naisen murhasta ja kun FBI oli yhteydessä hän huumaa naisen ja tappaa hänet.

a) Latasin uusimman Kali linux live tikun iso-kuvan Kalin kotisivulta versio: kali-linux-2025. 1a-live-amd64.iso. Käytin asennuksessa 4096mb muistia, 3 prosessoria ja 60gb kovalevy muistia.

b) Poistin kalin verkosta painamalla Ethernet Network kuvaketta oikeasta yläkulmasta ja valitsemalla disconnect. Tämän jälkeen avasin terminaalin ja kokeilin komentoa ping 8.8.8.8, josta tuli vastaus ping: connect: Network is unreachable.
Koitin myös avata Firefox selaimella YouTuben, enkä päässyt sivulle. ”Hmm. We’re having trouble finding that site.” ponnahti sivulle kun koittin avata YouTuben.

c) nmap -T4 -A localhost parametrit: 
-T4 tekee “Timing template”, joka määrittää skannauksen nopeuden (Nmap Man Options Summary).
-A valinta lisää skannaukseen käyttöjärjestelmä tunnistuksen ja versio tunnistuksen (Nmap Man).
-localhost on kohde johon skannaus tehdään, tässä tapauksessa oma virtuaali-kone.
Itsellä kun ajoin komennon nmap -T4 -A localhost sain vastaukseksi että kaikki 1000 porttia on ignore listalla ja 1000 tcp porttia on kiinni.

d) Asensin Apache2 ja openssh-serverin ja ajoin komennon nmap -T4 -A localhost uudestaan ja tällä kertaa tuloksissa on eroja. Skannaus löytää molemmat Apache2 ja openssh-serverin. Openssh on portti numerolla 22 ja se on aukinaisessa tilassa, ja Apache2 on portti numerolla 80 se on myös aukinaisessa tilassa.

e) Asensin Metaspoilable 2 VirtualBoxiin.

f) Tein koneiden välille virtuaaliverkon, jossa Kali koneen saa myös verkkoon kiinni, jos niin haluaa. Pingasin molemmissa koneissa www.google.com ja en saanut yhteyttä. Sitten kokeilin pingata Kali koneella Metaspoilable 2 konetta ja sain vastauksen takaisin. Käytin verkon asetuksiin Tuomaksen vinkkejä (Metaspoilable2 asennus).

e) Ajoin komennon nmap -sn [metaspoilable ip] ja sain vastauksen terminaaliin, että kyseisen ip:n host on päällä ja tarkistin selaimenkautta että, metaspoilable webbipalvelin oli päällä.

f) Metaspoilable rootshell portti 1524 on kiinnostava koska sillä voidaan mahdollisesti päästä metaspoilablen sisälle ja saada root oikeudet. Portti 3306 MySQL voi olla hakkerille kiinnostava portti koska kyseessä on tietokanta.

## Lähteet
Kalin kotisivu https://www.kali.org/get-kali/#kali-live
Nmap Man https://nmap.org/book/man.html
Nmap Man Options Summary https://nmap.org/book/man-briefoptions.html
Metaspoilable2 asennus https://tuomasvalkamo.com/PenTestCourse/week-2/
