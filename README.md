# Návrh databázy na predmet DBS
### Tomáš Oross, Otto Novak

Nami navrhnutú hru vedia hrať len používatelia, ktorí sú zaregistrovaní. Medzi registračné možnosti
patrí registrácia cez samotnú hru, registrácia cez Facebook a registrácia cez Google.

• Používatelia vedia byť priatelia. Priateľstvo je na pozvánku, ktorá môže byť aj
zamietnutá. Priatelia majú medzi sebou viditeľné postavy a dosiahnuté user questy.

• Používatelia vedia vytvárať tímy. Do tímu sa používateľ dostane len cez pozvánku,
ktorú môže potvrdiť, alebo zamietnuť. Z tímu môže kedykoľvek odísť. Každý tím má svojho správcu ktorý ako jediný dokáže posielať pozvánky do tímu iným hráčom. Hráči môžu tím kedykoľvek opustiť.

• Používatelia vedia spolu komunikovať cez chat. Komunikácia môže byť buď v rámci
tímu, alebo medzi jednotlivcami, ktorí sú však priatelia aby nedochádzalo
k neželanému spamu.

• Používateľ je v hernom svete reprezentovaný ako postava, ktorá môže mať jednu
z viacerých možných rol (napríklad mág, warrior alebo lukostrelec). Používateľ môže mať zároveň viacero postáv, no každá postava môže byť naraz iba na jednom leveli (poschodí) – teda čo postava to hra. Dôležitými parametrami postavy sú počet životov, útočne číslo a obranné číslo. Postava je jednoznačne identifikovateľná.

• Úlohou postavy je samozrejme zabiť finálneho bosa. Každá postava na určitom levely
sa však stretáva len s pekelnými príšerami ktoré súhlasia s levelom postavy – teda
takáto príšera má rozsah levelov v rámci ktorých sa zobrazuje postavám. Niektoré
príšery však majú špeciálnu podmienku, a to že sa zobrazia len ak používateľ už zabil
inú príšeru v hierarchii pred ňou alebo splnil požadovanú. Aby sa však postava vedela posúvať medzi levelmi tak každá zabitá príšera dá používateľovi EXP (experience) body. Príšera má obdobne ako postava počet životov, obranné a útočné číslo.

• Aby postava mohla zabiť finálneho bosa, tak okrem zabíjania je možné plniť aj úlohy,
za ktoré splnenie je XP. Jednotlivé úlohy sa viažu na územia mapy a tiež pre
jednoduchosť hry na zabíjanie určitého množstva príšer. Úlohy sú tiež viazané na LVL
postavy.

• Pre každú postavu je teda definícia, koľko EXP bodov musí používateľ získať aby
dosiahol ďalší level postavy. K levelom postavy sa viažu aj ďalšie schopnosti
v závislosti od role postav. Tieto schopnosti nie sú lineárne a postava si môže vybrať
z viacerých možnosti. Môžu na seba nadväzovať ale aj nemusia napr. LVL1 otvára
možnosť výberu schopnosti A, B a LVL 2 v prípade výberu A otvára možnosť C,D a LVL
2 so schopnosťou B otvára C a E. Schopnosti obsahujú teda stromovú štruktúru. Pre
jednoduchosť hry predpokladajte , že každá cesta umožňuje dosiahnutie rovnakej
úrovne v rámci stromovej štruktúry napr. úroveň 99, čím je možné zneškodniť vládcu
temnôt.

• Pri zvýšení LVL postavy získava postava navýšenie svojich základných parametrov
počet životov, útočne číslo a obranné číslo. Ich navýšenie sa viaže na rolu postavy.

• Ďalšia dôležitá časť je mapa, na ktorej sa všetko odohráva. Mapa je rozdelená na
poschodia (postava začne napr. v zrúcanine kostola a skončí za 20 pivničných
poschodí v pekle), ktoré sú sami o sebe pre jednoduchosť reprezentované ako
matica, kde je možné definovať na pozíciu či už nepriateľa, iného hráča alebo nejaký
predmet. Iný hráč pokiaľ nie je z vlastného tímu sa ráta ako nepriateľ.

• Predmet môže získať postava a zároveň ho môže no nemusí použiť. Predmet môže
zvyšovať jedno, alebo všetky parametre používateľa (obranné, útočné číslo, či počet
životov), ak je aktuálne priradený používateľovi. Predmety môže získať ako odmenu
za zabitie príšery alebo splnenie úlohy.

• Boj a auditovanie - dôležité je pamätať si za čo postava EXP body získala – koho
zabila, kde a za akých okolností, aby bolo možné hernú logiku auditovať a vytvárať
štatistiky progresu používateľov. Pre každý súboj si budeme ukladať jednotlivé
udalosti, ktoré sa v rámci súboju uskutočnili (Combat log).

