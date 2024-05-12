
# Cíl práce
Cílem mé práce bylo, navrhnout bázi znalostí skautských programů. S tím, že báze je specifikována jako systém umožňující co nejsnazší sdílení (zapisování) záznamů o programech připravených v rámci činnosti našeho oddílu a zároveň nabízející možnost správného a rychlého filtrování zobrazení (čtení) uložených záznamů, podle definovaných částí jejich obsahu. Kterýžto systém by zároveň, vzhledem k neziskové a dobrovolné povaze skautingu, nevyžadoval lidské ani finanční zdroje na svůj provoz či údržbu konzistence uložených dat.

Obsahem záznamů jsou pak chápány konkrétní části a parametry jednotlivých zaznamenaných programů (např. "Pro kolik dětí je hra vhodná?", "Kolik vedoucích je na hru potřeba?", ...). 
Proto bylo třeba definovat, co jsou to 'skautské programy' a jaké údaje, s nimi asociované, je vhodné v navrhované bázi ukládat, právě jako obsah jednotlivých záznamů, který pak umožní samotné jejich filtrování, při prohledávání (čtení) v bázi uloženého obsahu. Pro vyřešení tohoto dílčího problému byl v práci stanoven 2. dílčí cíl, který si klade za úkol vybrání výseče reality, která by v bázi měla být zaznamenávána.

Aby však, na základě získané definice domény skautských programů, bylo možné sestavit konkrétní strukturu navrhované báze, bylo nutné mít zvolený konkrétní softwarový nástroj, který by tvořil její infrastrukturu.
A protože požadavky na bází nabízené možnosti čtení a zapisování i vyžadované zdroje, stanovené hlavním cílem, jsou všechny záležitostí primárně zvolené infrastruktury, byl v práci stanoven 1. dílčí cíl, který si klade za úkol vybrání právě takové infrastruktury, která by nejlépe splňovala stanovené požadavky.

S vybranou infrastrukturou i definovanou doménou, jenž má být bází reprezentována, je tak posledním krokem, potřebným k dosažení hlavního cíle práce, sestavení schématu struktury pro údaje, které byly vybrány k ukládání ve vybraném databázovém nástroji. Proto je v práci stanoven 3. a zároveň poslední dílčí cíl, který si klade za úkol tuto strukturu získat.
# Použité metody
1.
Při výběru nejvhodnější infrastruktury jsou v práci posuzovány čtyři softwarové nástroje, každý využívající odlišnou datovou strukturu pro uložení záznamů.

Hodnocení nástrojů z hlediska nabízených možností zapisování obsahu je provedeno pouze pomocí jednoduché kritéria, které přijímá pouze nástroje umožňující zapisování bez nutnosti znalosti jiného než přirozeného jazyka v němž jsou zápisy realizovány. Kritérium tak efektivně zajišťuje, že navržená báze bude umožňovat uživatelům zapisovat její obsah pomocí rozhraní nepříliš odlišného od Dokumentů Google relativně k posuzovaným nástrojům databázového typu.
Z hlediska nabízených možností čtení uloženého obsahu je v práci využito hodnocení posuzovaných nástrojů pomocí tří kritérií a výběrem jediného nástroje, který je shledán z tohoto hlediska nejlepším. Základním kritériem byl požadavek na schopnost posuzovaného nástroje zobrazovat záznamy odpovídající zadanému dotazu, bez chyb prvního i druhého typu. Druhým kritériem hlediska možností čtení byl odhadovaný průměrný počet znaků vyžadovaný k napsání dotazu danému nástroji o zobrazení jen určité podmnožiny z uloženého obsahu. Posledním kritériem tohoto hlediska pak bylo, zda nástroj v základu poskytuje grafické webové rozhraní umožňující s ním interagovat.
Všechna kritéria tak mají za úkol pomoci určit, který nástroj nabízí nejsnadnější, zároveň bezchybné filtrování zobrazení uloženého obsahu.

Pro nástroje, vybrané hodnocením jednoho i druhého hlediska, je následně provedena analýza obsahu literatury publikované o daném nástroji. Účelem této analýzy bylo podrobnější charakterizování datových struktur v nichž nástroje ukládají zapsaný obsah, spolu s možnostmi programové komunikace s danými nástroji.

Posledním krokem při výběru infrastruktury je pak již jen identifikování konkrétního softwarového řešení pro použití v návrhu a ověření realizovatelnosti tohoto řešení pomocí implementace jeho klíčových funkcionalit.

2.
Co se obsahu navrženého k uložení týče, k jeho určení jsou v práci využity tři centralizovaná uložiště záznamů o skautských programech označovaná dále jako existující báze.

Pro existující báze, jsou za prvé identifikovány kvality zaznamenaného obsahu a za druhé vlastnosti báze, které jsou problematické z hlediska jejího využití jako interního nástroje oddílu. Tím je tak zároveň argumentována volba daných bází jako výchozí zdroje pro definování výseče reality navržené k zaznamenávání.

Obsah těchto, existujících bází, byl následně analyzován s primárním záměrem nalezení pojmů asociovaných s programy danou existující bází, které vyznačí výseč reality jenž bude dále modelována. 
Konkrétní způsoby získání hledaných pojmů se nicméně mírně lišily v závislosti na míře strukturovanosti jednotlivých bází. Pokud báze nabízela jasný popis struktury pro záznamy o programech byla identifikována konkrétní část té báze, ze které byly pojmy vybrány. V případě, že jasná struktura chyběla, byla provedena stručná rešerše daného obsahu a pojmy byly následně získány z ní.

Pro dokončení definice vybrané výseče reality je v práci využito diagramu tříd podle standardu UML. 
Konkrétně byla nejprve sestavena 'základní definice', která modeluje vztahy mezi množinou pojmů vzniklou sjednocením jednoho, až dvou pojmů z každé z existujících bází, které nejvýstižněji reprezentují, v ní uložené záznamy.
Následně byly všechny, z analýzy obsahu bází, získané pojmy roztřízeny, s pomocí vlastních doménových znalostí, podle jejich asociovatelnosti k jednotlivým třídám v základní definici. Dále byly modelovány vztahy mezi pojmy v rámci jednotlivých skupin přiřazeným třídám v základní definici, tím bylo docíleno minimálního počtu tříd nutných asociovat se základními třídami a navíc přesnějšího zobrazení reality. 
Na závěr konceptuálního modelování pak byly modelovány vhodné asociace mezi strukturami z pojmů získaných analýzou existujících bází a jednotlivými třídami v základní definici. Tím tak byla sestavena 'rozšířená definice' domény skautských programů.

Popsanou metodikou získaný diagram tříd je nakonec porovnán s modelem tvořeným rovněž pro navrhovanou bázi, nicméně primárně s využitím mých vlastních doménových znalostí, nikoliv systematickým zpracováním existujících zdrojů.

3.


# Dosažené výsledky
Na základě zjišťení z publikací o daných nástrojích je dále identifikována konkrétní infrastruktura odpovídající hlavnímu cíli práce

# Vlastní přínos autora

