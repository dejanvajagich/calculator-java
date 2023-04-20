# LOC Lines of code
LOC je 148.<br>
<br>
Start.java (19) <br>
Calculate.java (129) <br>
LICENSE (17 linija teksta koje nisu kod!) <br>

Ukupan broj linija za sva tri fajla je 235, 
od čega je lines of code bez praznih linija
i komentara tj. LOC = 165 za sva tri fajla
odnosno 148 ipak (bez LICENSE fajla, koji zapravo
ne sadrži linije koda, već samo tekstualni
zapis same licence). Tako, LOC iznosi 148.

# Ciklomatska i kognitivna složenost

Ciklomatska složenost za
metode evaluateExpression i Calculate
je niskorizična, 
<br> dok je kognitivna, kao i
uvek, nešto malo kompleksnija od ciklomatske. 

# Statička analiza koda
Generalno govoreći, klase bi mogle biti možda malo bolje dokumentovane, 
uz malo više Javadoc komentara koji bi bolje pojašnjavali funkcionalnost 
metoda i parametre koji se koriste. To bi zasigurno pomoglo boljem razumevanju 
samog koda za sve programere i članove tima koji rade na aplikaciji, ili prilikom 
njenog unapređenja nakon nekog dužeg perioda. <br>

Takođe, preporučljivo bi bilo praktikovanje
camelCase upotrebe, po Java konvenciji, u celokupnom kodu.

start.java 6. linija koda <br>
Varijabla Expression ima veliko početno slovo, 
što nije u skladu sa konvencijalnim nazivima varijabli u Javi. 
Preporučljivo bi bilo promieniti ime varijable na "expression"
uključujući i na ostalim linijama koda na kojima se pojavljuje,
ako to nije u suprotnosti sa nekim specifičnim razlozima.

start.java 12-13 linije koda <br>
Mnogo bolje bi bilo da je new Scanner objekat 
definisan izvan while petlje i samo upotrebljen u petlji.
Nije potrebno kreirati novi objekt Scannera u svakoj iteraciji petlje, 
već samo jednom pri pokretanju programa i zatvoriti ga nakon korištenja,
da ne bi bespotrebno samo opterećivali memoriju.

start.java 11-20 linije koda <br>
Takođe, ovom bloku koda nedostaje obrada izuzetaka u slučaju eventualnih grešaka prilikom unosa.
Ovaj kod ne proverava unose korisnika, što može dovesti do nepredvidivog ponašanja, 
neočeivanih rezultata i nepotrebnog prekida programa. Preporučuje se dodavanje obrade izuzetaka, 
npr. pomoću try-catch bloka i provera unetih podataka od strane korisnika,
u slučaju unosa nepotebnih karaktera, slova ili operatora, kao i deljivost unetih brojeva sa nulom, 
kako bi se izbegle greške.

start.java 19. linija koda <br>
Metoda Calculator.Run(Expression) se poziva unutar petlje, što može uzrokovati probleme 
s performansama. Preporučljivo bi bilo izvući ovaj poziv metode iz petlje 
i otpremiti rezultat u varijablu koja će se zatim  upotrebiti ili ispisati na konzoli.

calculator.java linija 4. linija koda <br>
Klasa Calculator bi mogla biti bolje struktuisana, tako da razdvoji logiku parsiranja izraza 
i izračunavanja rezultata u zasebne metode.

calculator.java linija 6. linija koda <br>
Varijabla finalResult je deklarisana kao static, 
što znači da će zadržati svoju vrednost između poziva metoda. 
Ovo bi moglo dovesti do neočekivanih rezultata ako bi se klasa Calculator 
koristila na više mesta u aplikaciji. Umesto toga, varijablu finalResult 
bi mogli deklarisati kao lokalnu u metodi evaluateExpression() ako to više
odgovara daljem ili finalnom konceptu i zamisli same aplikacije.

calculator.java linija 15. linija koda <br>
Konstruktor klase Operations je deklarisan privatnim, ali klasa nema nikakvih (privatnih) varijabli 
koje bi mogle biti inicijalizovane putem konstruktora. Možda je ovo čak i nepotrebno ukoliko se
sam kod ne bude dopunjavao u nekom pravcu u kom to ima više smisla.

calculator.java linija 18. linija koda <br>
Preporučuje se upotreba camelCase konvencije prilikom imenovanja metode ToString prema konvenciji Java koda,
osim ukoliko to nije u suprotnosti sa nekim specifičnim razlogom.

calculator.java linija 28. linija koda <br>
Metoda evaluateExpression() ima prilično dugačku i složenu logiku koja bi se mogla pojednostaviti 
razdvajanjem parsiranja izraza u zasebne metode.
Takođe, u slučaju greške, metoda evaluateExpression() vraća "ERROR" u tekstualnom formatu, 
što nije najbolji način za označavanje i detaljnije razumevanje eventualne novonastale greške u Java kodu. 
To bi se moglo rešiti upotrebom izuzetaka ili upotrebom neke druge podrobnije oznake za opis vrste greške
koja je izbila.

calculator.java linija 69. linija koda <br>
Metoda Calculate() takođe ima složenu logiku koja bi se mogla pojednostaviti, 
recimo korištenjem for petlje umesto niza if izjava, ukoliko zamisao projekta to dozovljava.
