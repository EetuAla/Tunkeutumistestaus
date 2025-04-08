# h2 Täysin laillinen sertifikaatti
## x) Tiivistelmät
Broken Acces Control https://owasp.org/Top10/A01_2021-Broken_Access_Control/
- Tarkoitus valvoa ettei käyttäjät voi toimia omien oikeuksie ulkopuolella.
- Mikäli tässä epäonnistutaan voi se johtaa tietojen muuttamiseen, luovuttamiseen tai jopa tuhoamiseen.
- Yleisimpiä heikkoiksia on esimerkiksi, URL osoitteen muokkaus, pääsy API:hin jossa on PUT, POST ja DELETE oikeudet.

Server-Side Request Forgery (SSRF) https://owasp.org/Top10/A10_2021-Server-Side_Request_Forgery_%28SSRF%29/
- SSRF ongelmat ilmenevät kun web sovellus ei tarkasta käyttäjän antamaa URL-osoitetta kun se hakee resursseja.
- SSRF hyökkäykset yleistyvät kun nykyaikaiset web sovellukset lisäävät käyttäjille yhä kätevämpiä ominaisuuksia.
- Hyökkäyksien vakavuus myös kasvaa kun yritykset ovat vaihtaneet pilvipalveluihin ja arkkitehtuurista on tullut monimutkaisempi.

Insecure direct object references (IDOR) https://portswigger.net/web-security/access-control/idor
- IDOR on osa Broken Acces Control haavoittuvuutta.
- IDOR on eräänlainen pääsynhallinnan haavoittuvuus, joka syntyy kun sovellus käyttää käyttäjän toimittamaa syötettä päästäkseen objekteihin.

Path traversal https://portswigger.net/web-security/file-path-traversal
- Path traversal, joka tunnetaan myös nimellä directory traversal on eräänlainen haavoittuvuus, joka esiintyy usein verkkosovelluksissa.
- Path traversalin avulla hyökkääjä voi päästä käsiksi tiedostoihin ja hakemistoihin, joihin hänellä ei pitäisi olla pääsyä. Esimerkiksi palvelimen salasanoihin.

Cross-site scripting https://portswigger.net/web-security/cross-site-scripting
- Cross-site scripting (XSS) on kolme pää hyökkäys tyyppiä, Reflected XSS, Stored XSS, DOM base XSS
- Reflected XSS, jossa haitallinen scripti tulee nykyisestä HTTP-pyynnöstä se heijastuu takaisin käyttäjälle eikä tallennu palvelimeen.
- Stored XSS, jossa scripti ladataan verkkosivin tietokantaan, ja suoritetaan kun käyttäjä lataa sen sisällön.
- DOM based XSS, haavoittuvuus on selaimen koodissa, scripti muokkaa sivun rakennetta hyödyntämällä URL parametrejä.
  
