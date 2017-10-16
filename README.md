# maps-website

Selenium test for maps-website

"Maps-website" projekat je framework za testiranje Maps website-ova.
Predvidjeno je da se koristi uz pomoc pytest framework-a, pa je isti potrebno instalirati kao plugin za python (pip install pytest).

Framework se satoji od ovim package-a:
1. base: tu se nalaze metode koje su upostene za sve webpage-eve, tj. ne zavise od samog contenta page-a. Znaci tu idu metode koje su zajednicke za sve pages-a
2. confgfiles: tu idu konfiguracioni podaci
3. pages: tu ide py fajlovi podjeljeni po web pages, sav kod i promjenjive za web pages se tu nalaze
4. screenshots: ovdje se generisu screenshots koji se pravi u selenium_driver py fajlu
5. test: ovdje se nalaze testovi koji se izvrsavaju, podjeljeni po web pages. odavde se pozivaju klase koje se nalaze u pages paketu kao i klase koje se nalaze u base paketu
6. utilites: ovdje se nalaze neke upostene funkcije, npr. manipulisanje stringovima i sl. neke generalne f-je sa neta bi se ovdje mogle stavljati

primjer izvravanje nekog testa:

py.test homepage_tests.py --project MapsPilot --browser ff --domain mapspilot.com

--project je obavezan. Potrebno ga unijeti u originalu kako se korisit na web pageevima (voditi racuna o kapitalizaciji). Primjer: MapsPilot.
--browser je opcion. Moguce vrijednosti su: ch, ff, ie. Ako ga nema default vrijednos je ch.
--domaine je opcion. Predstavlja domian name, ako ga nema isti se po default kreira kao project+'.com'.
                     To znaci ako je domen drugaciji od .com onda je obavezno proslijediti domain name. Primjer: mapspilot.com (kapitalizacija nije bitna).

Testove je moguce pokrenuti i u nizu (test suite). Za to je potrebno pokrenuti test_suite.py. A u njemu podesiti koji ce se testovi izvrsavati
