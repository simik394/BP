



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


# metodika -teorie v1
## Mapování pojmů asociovaných se skautskými programy z existujících bází skautských programů
### Obecný postup %% fold %%
~~Abych zjistil jaké informace jsou relevantí pro zaznamenávání v bázi skautských programů, provedu analýzu literatury z této oblasti.~~
*Naštěstí nejsem první kdo se rozhodl něco o skautských programech zaznamemat a shromáždit na jedno místo. Takže nyní mám k dispozici dokonce několik zdrojů, které obsahují menší či větší míru sebraných záznamů z této oblasti. Konkrétně vím o třech, všech poměrně hodných analýzy.* Ikdyž každé pro mírně odlišné informace.
Právě kvůli jejich různosti jak ve formě, tak v obsahu bude káždá z bází analyzována postupem, který se v konkrétních podrobnostech získání pojmů bude lišit pro každý zdroj. 
Nicméně všechny analýzy sdílí stejný rámcový postup, jelikož všechny přeci jen mají za **cíl identifikovat z báze programů pojmy asociované s programy**.
Pro dosažení tohoto cíle, je pro každou z bází nejprve prozkoumáno jaké pojmy jsou použity k pojmenování prvků báze umožňující zobrazit skupinu záznamů sdílejících určité vlastnosti. Dále je pro tento krok používán název 'prozkoumání vnější struktury záznamů v bázi'. Vnější proto, že při jeho provedení není potřeba zobrazovat přímo obsah konkrétních záznamů, ale je provedeno pouze v rozsahu ve kterém analyzovaná báze umožňuje zobrazovat pouze záznamy sdílející dané vlastnosti.
Na druhou stranu záznamy mohou obsahovat i nějaký pojem, podle kterého *akorát* daná báze nepodporuje vyhledávání. Z toho důvodu jsou v dalším *kroce* vybrány konkrétní záznamy a je prohledán obsahu, každého z nich a hledány pojmy asociované s daným záznamem, o*pakující se ve více částech z vybraného vzorku*. (Vzorkem je myšlena sada záznamů systematicky získaná z báze. Část vzorku je tedy jeden konkrétní záznam.) Proto je dále na tento krok odkazováno jako na 'prozkoumání vnitřní struktury záznamů v bázi'. 
Všechny pojmy získané z těchto i dodatečných kroků analýzy existujících bází, představují základ, ze kterého budou na začátku praktické části vybírány *části* pro vytvářený konceptuální model. 

### chystamprogram %% fold %%
==První== představuje stránka chystamprogram.skaut.cz, jedá se o web vytvořený organizací Junák - český skaut, která zároveň za celý obsah zcela zodpovídá. [[../../myDM/Zotero/LiteratureNotes/ChystamProgramOProjektu#^NMC5UM33aSNYTTS96]]
Znamená to, že pokud *budete chtít* nějakým *vašim* programem bázi obohatit, musíte být přihlášeni účtem ze skautISu a poté váš návrh na přidání musí *projí* kontrolou. *Nevím jaký, jestli nějaký vliv to může mít na různorodost a počet zaznamenaných aktivit.* 
Avšak díky tomu bývají zaznamenané aktivity napojeny na nějaký bod ze Stezek.
Což je dobré a užitečné proto, že stezka nepředstavuje jen rámec pro děti, podle kterého by se mohly samy všestranně rozvíjet. Rovně ale jako pomůcka pro vedoucí, když připravují vhodný program pro nadcházející schůzku například. [[myDM/Zotero/LiteratureNotes/StezkyCestickyVlcat#^N5AJVIHJa43Y7SWYU]]
Přinejmenším *tuto vlastnost* aktivit bych chtěl, s ohledem na cíl práce, každopádně zachytit i v bázi navrhované.
Ovšem na chystamprogram je *toto* hlavní, nikoliv jediný způsob kategorizace aktivit.

- [x] Pro prozkoumání vnější struktury zaznamenaných aktivit. Průzkum provedu prohledáním rozklikávacích nabídek možností u políček filtrů ve vrchní části stránky.

- [x] Vnitřní *struktura* záznamů v této bázi mohu určit na základě formuláře pro přidávání nových aktivit. V tom jsou všechny použitelné položky pojmenovány a opsány tím co by měly obsahovat v případě že se jedná o textové pole. Je však jedno textové pole, které žádný popis nemá, pouze název "Obsah aktivity". Abych zjistil co přesně to znamená, případně jaké pojmy se vyskytují v rámci tohoto textu v záznamech. Použiji vzorek z báze, stačí mi však menší, než kdybych se pomocí něj snažil najít všechny možné hledané pojmy. Jako budu muset u poslední báze, která žádnou takovouto šablonu nemá.

- [ ] Vlastní provedení se skládalo z vybrání deseti záznamů, které *mají zapsány analyzovanou* část, každý získaný z výsledků jiného filtru, aby byla snížena šance na nenalezené pojmů typicky používaných pouze v Podskupinách, které jsem neprohledával. A zároveň jsem nemusel procházet násobně více záznamů.

- [x] Navíc tato báze, *odpovídajícně* své podstatě, obsahuje ještě stránky 'Metodika' a 'O Projektu'. Jelikož se jedná pouze o dvě, navíc poměrně krátké stránky. Avšak plné pojmů. Z těch vyberu pojmy pro modelování jednoduše manuálním přečtením a získáním pojmů splňujících cíle sdíleného rámcového postupu, pokud nějaké nové budou obsaženy.
### Encyklopedie her %% fold %%
==Druhá== báze je prozměnu v tištěné podobě a narozdíl od předchozí, se tato encyklopedie věnuje pouze hrám, zato velmi podrobně. 
Celým názvem 'Velká encyklopedie her', je tvořena čtyřmi samostanými tituly vydanými mezi lety 1987-1988 autorem ?Zapletalem. 
Přičemž každá z nich sdružuje hry vhodné do jiného prostředí a má přibližně 600 stránek. Sice menšího formátu, ale i přesto se často vejdou i dvě hry na stránku. Konkrétní počet zapsaných her neznám, ale předpokládám, že bude podobně působivý. Při této volbě spoléhám na předpoklad, že myšlenka zábavy a her před třiceti lety a dnes, ač se mohou lišit. Nebude odlišná natolik, aby většina tvrzení v těchto encyklopediích byla zastaralá do úrovně nepoužitelnosti. Pokud by i jen část zůstala aktuální. Mají vzhledem k objemu základu pořád šanci, že naúkor dekádám by mohla zůstat poměrně obohacující základna znalostí.

- [x] Pro určení vnější strukturu záznamů budou využity názvy kapitol a samotných knih. Navíc však i podkapitola 'Úvodní kapitola' v každé z encyklopedií, definující zkratky a symboly, které ač limitované fyzickou formou knihy, stejně částečně umožňují zobrazovat si jenom aktivity se specifickou vlastností, když listujete stránkami a rozhodujete se na základě uvedených zkratek a symbolů, zda číst dál, nebo pokračovat v hledání. Odpovídají tak také požadavků vnější struktury.
- [x] 
- [ ] *Vzorek k prozkoumání vnitří struktury zaznamenaných her bude vybrán tak, aby obsahoval z každé kapitoly **dvě** hry, vždy tu první a prostřední v dané kapitole. Z něj pak budou vybrány pojmy opakující se alespoň v **pěti** částech vzorku.*
### Sdílený disk našeho oddílu %% fold %%
==Třetí== analyzovaná základna znalostí je velmi unikátní kousek. 
Byla totiž vytvořena členy našeho oddílu. Není zrovna utřízená, ani obsáhlá. Nicméně reprezentuje informace, které sami cílové uživatelé mého systemu, Považují za důležité.

A vzhledem ke skutečnosti, že můj systém trochu spoléhá na to, že do něj budou zapisovány údaje. Je důležité aby jim zaznamenávané údaje dávalo smysl, jinak se totiž do báze nedostane dostatečný objem dostatečně obohacených znalostí, aby mohla nabízet hledaní, kterému se vyplatí věnovat čas a sestavit pro ně dotaz.

Proto výsledkům z její analýzy přikládám při navrhování systému vyšší váhu, než zbylým dvěma základnám. Dalším mým štěstím je, že dokumenty jsou sice posbírané namátkove, ale jejich uložení na sdílenem disku není tak chaotické, jak by mohlo být.

- [ ] To znamená, že existuje záznamům externí struktura pojmenovaných objektů, které rozdělnie záznamy do skupin podle určitých jejich vlastností. Mohu ji tedy prohledat pro nalezení pojmů, využitých k pojmenování těch objektů. K prozkoumání této struktury, podobně jako minule, budou použity názvy složek a souborů na disku. Nebudu ale prohledávat jiné záznamy, než ty s programem. Ostatní, jako seznam členů a další primárně uložené kvůli administrativě vynechám.

- [ ] Vnitřní struktuře nicméně tentokrát budu, vzhledem k původu báze, více pozornosti, než v prvních dvou případech. Konkrétně tak, že jako vzorek použiji alespoň 40% ze všech záznamů o programech na sdíleném disku. Navíc, vzhledem ke skutečnosti, že disk obsahuje i archivní zápisy k některým výpravám až z roku 2012. Pro výběru vzorku platí podmínka na minimálně 2/3 záznamů musí být z posledních 5 let. Starších než 5 let může být zahrnuto maximálně 1/3. Vzorek pak už zpracovávám obdobně jako dříve. Čili vyznačím pojmy asociované se záznamem a spočítám frekvence jejich výskytu ve vzorku. Načež pokud je pro pojem získána vyšší hodnota frekvence než 20% z počtu částí vzorku, Je pojem přidán mezi kandidáty na část konceptuálního modelu. 
## Výběr infrastruktury %% fold %%
Kromě údajů, které by se měly ukládat, je také zásadní otázkou, jak a kde budou záznamy skutečně uloženy. Toto rozhodnutí ovlivňuje mimo konceptuální model všechnu další práci. Bylo by proto dobré mu nějaký prostor věnovat a zjistit pár informací o uložištích kandidátech. Zmíněnými kandidáty jsou g Docs jako baseline. Dále g Sheets jakožto kompromis mezi databází a prostředím dokumentů. Třetím kandidátem je relační databáze MySQL. A nakonec databáze Neo4j jakožto reprezentace NoSQL.
### Podmínky pro výběr
Z cíle této Práce jsou odvozeny základní podmínky pro navrhovaný systém. Konkrétně se jedná o podmínky:
1. Zápis
- alespoň stejně uživatelsky přívětivý jako aktuální řešení.
2. Čtení
- efektivní přístup (rychlý A Přesný)
- Čím strmější křivka učení daného nástroje pro nového, nebo začínajícího uživatele, tím horší..
### Získání výsledků o míře plnění podmínek softwarovými kandidáty
Pro každého z kandidátů je pak nejprve určena uživatelská přívětivost při zápisu do struktury. Není však určována absolutním číslem, ale vyjádřena seřazením variant od nejlepšího po nejhorší v míře podpory daném aspektu funkcionality. Rozhodnutí o pořadí je provedeno na základě údajů získaných hledáním v dokumentacích k daným softwarům.
Hledání ukončím když dám dohromady dostatek argumentů, jenž by my umožnily přesvědčivě obhájit zvolené pořadí sw kandidátů z hlediska míry naplnění sledovaného cíle.
Na otázku čtení získám odpovědi obdobným způsobem jako pro psaní, pouze modifikují parametr ve vyhledávání.
### Získání infrastruktury
Na závěr využiji výsledky získané v předchozích dvou krocích. Vyhodnotím je oproti, požadavkům odvozeným z cíle práce. A sw, který vyhovuje oboum stanoveným kriteriím, vyberu jako infrastruktura pro navrhovanou bázi. 


## 

### metodika -praxe %% fold %%

Z relačního modelu, který je z konceptuálního modelu velmi snadné získat. Umožňuje převod možný pomocí "naivního" algoritmu[], který převede 

tabulka -> lable;FK → relationship; row → node; (column) Prop-> properties 
↳ může produkovat neoptimalné graf strukturu. 

Cypher avšak v základu podporuje funkce pro snadné refaktorování uložené dat. [ ] A v různých oficiálních literárních zdrojích je poté možné dohledat  [ ]
V této práci se však pokouším získat optimalizovanou (dělá to co potřebujeme s minimalizovanou náročností) schema pro GDB pomocí aplikace doporučení nejdříve na konceptuální model. A z ně pak odvodit vhodné schema pro 'naše využití'. 
S tím, že 'naše využití' bude popsáno sadou kompetenčních otázek odpovídajících rozsahu schopností existujících bází (tzn. Otázky na které 'umí odpovídat'). V teoretické části proto tedy představím ta doporučení, která budou při tvorbě aplikována. Jak konkrétně ovlivnila proces tvorby a jeho výsledek, popíšu v kapitole Návrh schema DB. Spolu s představením samotného výsledku.

docs schema + apps scripts
chtěl jsem. fungují. viz ověření realizovatelnosti, ale není kapacita se jim v této práci věnovat.



### Ověření validity konceptuálního modelu

### model pojmů
*Tvorba bude probíhat tak, že z nalezených pojmů budou vytvořeny třídy (v modelu obdélníky). Ty pak v modelovacím nástroji (draw.io) budou roztřízeny takovým způsobem, aby vzdálenost mezi každýma dvěma odpovídala přibližně jejich "příbuznosti", či podobnosti. Následně bude provedeno modelování povinných vztahů mezi třídami, počínaje hierarchiemi pojmů, respektive zachycení vztahů mezi specializovanými podtřídami a z nich generalizovanými třídami. Právě ve shlucích podobných pojmů bude modelování započato, protože mají nejvyšší pravděpodobnost na výskyt těchto hierarchických vztahů. Po vytvoření této struktury bude pokračováno modelováním volitelných vztahů mezi třídami.



### Názvy kapitol %% fold %% 
První kniha využívající pojem 'hry v přírodě' jako název je rozčleněna podle následujících kapitol:
- 'hry na louce' dále členěné do podkapitol (hry bez pomůcek; hry s oblázky a kameny; hra s kolíky, hůlkami a pruty; hry s dřevěnými válečky; hry s míčem; hry s malým míčkem; hry s hadrkoulemi; hry s šátkem; hry s různými pomůckami)
- 'hry v lese' dále členěné do podkapitol (běžecké hry; pátrací hry; hry s plížením; stopařské hry; orientační hry; bojové hry; pokladové hry; hry s pohádkovými motivy; didaktické hry; různé hry v terénu)
- 'hry ve zvláštním prostředí' dále členěné do podkapitol 
  {hry na cestě do přírody; hry v pochodu; hry v noční přírodě; hry v letním stanovém táboře; hry ve vodě; hry na plavidlech; hry na sněhu}
- 'dlouhodobé hry' dále členěné do podkapitol 
  {stopami statečných; tábor kosmonautů; město v džungli; zlatá horečka}

Druhá kniha s pojmem 'hry v klubovně' jako název, je rozčleněna podle následujících kapitol:
- 'Hry rozvíjející intelektové dovednosti' dále členěná na části:
	- 'O vítězství rozhodují jen hráčovi schopnosti', kterážto část je dále dělena na podkapitoly 
	  {Hry cvičící pozornost a postřeh; Hry cvičící paměť; Hry cvičící smysly; Hry, při kterých se řeší různé problémy; a) Hry bez pomůcek; b) Hry s psacími potřebami; c) Hry s deskou a hracími kameny; d) Hry s různými pomůckami; Hry cvičící důvtip a vynalézavost; Hry ověřující a rozlišující vědomosti}
	- 'O vítězství rozhodují hráčovi schopnosti i náhoda', kterážto část je dále dělena na podkapitoly 
	  {Hry s kartami; Hry s kostkami; Hry s dominem}
- 'Hry cvičící předevśím motoriku' dále členěná na podkapitoly 
  {Hry s kartami; Hry s kostkami; Hry s dominem; Hry rozvíjející rychlost; Hry rozvíjející sílu; Hry rozvíjející obratnost; Hry cvičící nervosvalovou souhru; Hry cvičící orientaci v prostoru}
- 'různé hry bez výcvikového významu' dále členěná na podkapitoly 
	{Seznamovací hry; Hry pro pobavení; Hadačské hry; Loterie}

Třetí kniha s pojmem 'hry na hřiště a v tělocvičně' je rozčleněna podle následujících kapitol:
- 'hry na hřišti' dále rozdělené do podkapitol 
  {Běžecké hry; Skokanské hry; Hry s házením a chytáním; Hry s kopáním; Hry s odpalováním; Hry s orientací v prostoru bez zrakové kontroly; Cyklistické hry; Různé hry; Herní cykly;}
- 'hry v tělocvičně' dále dělené do podkapitol
  {Běžecké hry; Skokanské hry; Hry s házením; Hry s kopáním; Hry s odbíjením; Hry s koulením; Bojové hry; Taneční hry; Různé hry; Herní cykly}
  
Čtvrtá a poslední kniha Velké encyklopedie pak nese v názvu pojem 'Hry ve měste a na vsi' a je rozčleněna do kapitol:
- 'Tradiční (i netradiční) dětské hry' členěna do částí:
	- 'hry na chodníku' dále členěnou do podkapitol 
	  {1. pohybové hry bez náčiní; 2. Hry s kamínky; 3. Hry s kuličkami; 4. Hry s fazolemi; 5. Hry s mincemi; 6. Hry s míčkem; 7. Hry se švihadlem; 8. Hry s různým náčiním;}
	- 'hry na plácku za humny' dále členěné do podkapitol
	  {1. Pohybové hry bez náčiní; a) Běžecké hry; b) Hry rozvíjející sílu; c) Hry s tradičním dialogem; d) Hry se zpěvem a tancem; e) Různé hry hry bez pomůcek; 2. Hry s míčkem; 3. Hry s míčem; 4. Hry s kameny; 5. Hry s pruty, hůlkami a kolíky; 6. Hry s nožem; 7. Hry s různými pomůckami;}
	- 'hry v městských ulicích' dále nečleněná podkapitola, obsahující pouze konkrétní hry.
- 'Netradiční hry ve městě' dále členěná do podkapitol 
  {l. Pozorovací a pátrací hry; 2. Bojové hry; 3. Detektivky; 4. Historické hry}