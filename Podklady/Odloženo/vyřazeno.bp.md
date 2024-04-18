



vlastně bych mohl nepočítat s časem na zápis, protože stejně se to "jakoby zapisuje", já řeším jenom přenos do DB aby v nich šlo hledat.
btw. Cokoliv mimo čtení a zápis do DB je mimo možnosti měřit. A to i ta DB je diskutabilní.

Vlastně bych mohl udělat i malinkatý odhad toho kolik času to naoplátku ušetří.

~~Výstup:: flowchart, možná kód~~
\*3 modelové situace na využití navržené báze ( kompetenční otázky? ) -estimatedProfiling-> 
Jak započítám zvyšující se ušetřený čas s každým vyhledáním? Budu to počítát také jako změnu údajů, která je potřeba zrcadlit?
Porovnat bez/s automatizací synchronizace.
V závislosti na naplněnosti báze = kolik bylo zapsáno? -> Zvyšuje šanci na úspěch při hledání, ale celkový čas potřebný k zápisu je úměrně vysoký počtu zapsaných informací.
V závislosti na důkladnosti přípravy a provedení.
v závislosti na počtu vyhledání s nalezením a vyhledáním bez nalezení, a po jaké době.
V závislosti na schopnosti uživatelů používat systém. (tuhle var můžu téměř eliminovat šblonama)

*Úkol průzkumu vnitřní struktury pak bude zjistit, zda se nějaké pojmy vyskytují i v samotném obsahu záznamů, mimo filtrovatelnou 'hlavičku'. Odpověď určím pomocí vzorku vybraného následujícím způsobem. Pro každou možnou hodnotu v jednotlivých filtrech provedu vyhledání obsahu. Zjistím kolik záznamů bylo nalezeno, a vyberu druhý zobrazený jako součást vzorku. Ze sestaveného vzorku pak vyberu pojmy na základě cílů sdílených s ostatními částmi analýzy jednotným rámcovým postupem a pokud se opakují ve více než 3 záznamech ze vzorku.*