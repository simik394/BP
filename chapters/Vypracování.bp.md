--- 
aliases: 
up: 
  - "[[Prods/120-BP/README|README]]"
---

#####  Dotazy %% fold %%
- jak moc bych měl popisovat výsledný model? Stačí stručně argumentovat jednotlivé prvky, proč jsou modelovány tak jak jsou?

##### ToDo %% fold %%
- [ ] [Ttyp::DODĚLAT]|[Cdist::1]|[HHTD::8] 🚧💣🚧  [treq::180]  %% fold %%
     ||:  #p/bp/teorie/sw/vyhodnoceníVýsledkůAnalýzy #p/bp/core   %% fold %%
      {není potřeba mít hotovou dříve než přijde na řadu realizace ověřování úspěšnosti dosažení výsledků (protože klíčové funkcionality jenž je třeba ověřit implementací)}
  
- [ ] [Ttyp::UDĚLAT]|[Cdist::1]|[HHTD::6] 🚧💣🚧 #p/bp/vypracování/schemaDB/bestPractices popsat nejlepší praktiky pro modelování grafů v Neo4j (postupně jednotlivé prvky(4))

- [ ] [Ttyp::UDĚLAT]|[Cdist::2]|[HHTD::12] 🚧💣🚧 #p/bp/vypracování/schemaDB/transform popsat provedené transformace vycházející z best practices a na výsledku vysvětlit jak se projevily %% fold %%
	- [ ] [testm::40min]|[HHTD::3]|[%targ::0]|[wtarg::200] - lables + nodes
	- [ ] [testm::30min]|[HHTD::3]|[%targ::0]|[wtarg::100] - relationships
	- [ ] [testm::40min]|[HHTD::3]|[%targ::0]|[wtarg::200] - properties
---



# -! | Infrastruktura pro bázi 
Tato sekce je ...%%**(Vyhodnocení výsledků analýzy (sw))** %% 
## Předpoklad
Jak bylo stanoveno v metodice, tato část popisuje infrastrukturu (softwarové nástroje) do základu navrhované báze, která by v souladu s cílem práce (viz. Cíl), nevyžadovala víc prostředků na údržbu, než sama ušetří a zároveň přitom odpovídal  i ostatním požadavkům Cíle.

Konkrétně, vzhledem k tomu, že aktuálně není k dispozici způsob, jak změřit ušetřený čas při využívání báze, je vycházeno z předpokladu, že pokud budou vyžadovány lidské či finanční prostředky na to, aby byl obsah v gDocs udržován konzistentní s obsahem v efektivně prohledatelné databázi, nebude ušetřený čas větší, než ten vyžadovaný na údržbu. 

## Infrastruktura pro navrhovanou bázi
### Vizualizace zjištění integrovatelnosti
![[gWorkspace-SW Mapa.jpg]]
![[neo4j-SW Mapa.jpg]]
Oba uvedené diagramy jsou založené opět na UML, i když i v tomto případě je učiněna drobná odchylka od standardu. Aby totiž uvedené diagramy odpovídaly normě, musely by obdélníky představující třídy, ještě mít menší čtverečky po stranách, kterými by byly reprezentovány konkrétní porty, které daná třída má a spojení s ostatními by pak měla být realizována pouze přes ony porty.
Jelikož se jedná jen o vizalizaci výsledků z předchozího kroku, nezahrnují diagramy žádnou informaci, která už by nebyla řečená. Nicméně pro vysvětlení použité notace, následuje stručný popis získané mapy možný integrací (propojení mezi softwary).
Jednodušší z obou diagramů zobrazuje dvě různé varianty databáze Neo4j, verze Aura je cloudová služba, která nabízí i celkem dostatečný objem možný k využití a bylo proto původním plánem vystačit při návrhu s ní, aby nebylo nutné nasazovat svoje vlastní řešení. Bohužel, jak je patrné z vizualizace a jak bylo rovněž už i řečeno, cloudová verze databáze  podporuje pouze komunikaci skrze knihovny, které si uživatel musí nejdříve nainstalovat (uložit spustitelný soubor do 'cesty' konkrétnímu programu). Což by ani nepředstavovalo problém, pokud tedy zrovna není potřeba s databází komunikovat z prostředí, kde si takové knihovny nainstalovat nelze, jako je například Apps Scripts. [kostyukMasteringNPMModules2023]
Posuzovaná množina softwarů tak nechává pouze jedinou možnou cestu (HTTP), která může být využita k programovému zrcadlení údajů z dokumentů do databáze.

### Vyplývá ze zjištění
Aby bylo možné
1. zapisovat do báze alespoň tak snadno, jako je to možné nyní
2. v krátkém čase, zobrazit (číst) pouze ty uložené záznamy, jenž skutečně vlastní hodnotu atributu zadaného v dotazu
3. provozovat navrženou bázi s nulovými náklady na infrastrukturu a minimálním časem potřebným na údržbu báze (konzistence dat mezi rozhraním pro zápis a rozhraním pro čtení),
musejí pro jednotlivé požadavky, níže vypsaná tvrzení, být pravdivá. Přitom je vycházeno z předpokladu, že uživatelská rozhraní budou fungovat a uživatelé je budou umět používat

Klíčové prvky z hlediska realizovatelnosti návrhu splňujícího stanovené požadavky:
1. úroveň uživatelské zkušenosti při zapisování do báze
	- Byl ponechán aktuálně používaný nástroj pro záznam informací v digitální podobě, nebo bylo zvoleno nějaké, z hlediska nových uživatelů, přívětivější řešení.

2. správnost a spolehlivost vyhledávání v uloženém obsahu
	- Rozhraní pro čtení uloženého obsahu, dokáže odpovídat na otázky o svém obsahu bez chyb prvního i druhého typu

3. minimální lidské i finanční zdroje, vyžadované na provoz
	- obsah z gDocs je možné číst s pomocí AppsScripts
	- je možné s pomocí AppsScripts přistupovat pouze ke specifickým částem dokumentů na základě jejich absolutního i relativního umístnění ve struktuře dokumentu
	- je s pomocí AppsScripts možné komunikovat s Neo4j
	- free self-hosting


## -! | Ověření realizovatelnosti navržené infrastruktury
Demo proces automatizované údržby konzistence uložených dat mezi rozhraními 
Je však důležité mít na paměti, že se jedná pouze o prostředek pro ověření předpokládané funkcionality, je tak opravdu jen v nejtutnějším rozsahu
### Struktury
Aby bylo možné vyzkoušet, že nástroje fungují, je nutné je testovat na nějakých datech. Protože konkrétní struktura pro navrženou bázi ještě nebyla vypracována, je pro ověřovací implementaci definována modelová struktura zaprvé dokumentu (naspisy, záhlaví, ...) a zadruhé báze. 
Pro ověření využitá struktura dokumentů, vychází z předpokladu, že pro jednu aktivitu bude vyhrazen běžně jeden dokument. Ale počítá i s variantou kdy by v jednom dokumentu bylo zahrnuto více než jedna aktivita, například pokud by se jednalo o lehce odlišné variace jedné hry. Zároveň je ale možné ukládat i dokumenty, které jsou vyhrazeny pro přípravu jedné konkrétní události, pro je potřeba umět mezi těmito dvěma druhy dokumentů rozlišovat. 
Aby toho byl script schopen, byl do dokumentové struktury nejprve zvolen prvek záhlaví, který obsahuje text 'Aktivita' pokud tomu obsah dokumentu odpovídá. Zároveň je tak provedena i přípravana situaci, pokud by mělo být načítáno více růných typů dokumentů, je pak i přesto možno v kódu scriptu využívat tu stejnou funkci.

Kromě záhlaví byl testovací dokument tvořen dvěma nadpisy úrovně jedna a pod každým z nich, přesně do elementu s id o jedna větší, než je id daného nadpisu, je umístěna tabulka se dvěma sloupci jenž má slouži pro jasné rozlišení parametrů reprezentovaných klíčem a přiřazenou hodnotou.

V databázi pak byl byly vytvářeny vrcholy pro jednotlivé dokumenty ze kterých se obsah načítal a k nim vztahm připojené vrcholy reprezentující konkrétní aktivity zapsané v daném dokumentu. U nahraných aktivit byly pak připsány odpovídající vlastnosti, pokud aktivita v dokumentu měla nějaké uvedené.

Samotná databáze byla pro tento účel hostována na Oracle Cloud Infrastructure, který nabízí dostatečný free tier, aby poskytoval zcela dostatečný prostředek.

### Proces
#### Vývojový diagram
![[flowchartAppsScripts Proof Implementace.jpg]]


# -! | Model pojmů
## Základní definice
### model 
 ![[Pasted image 20240425140659.png]]
### Program
Jedná se o nejobecnější z pojmů. Prakticky je programem cokoliv co připravujeme v rámci činnosti oddílu. 
Kdyby Činnost oddílu byla mezi modelovaným, pojmy, nacházela by se ta, na vršku generalizační struktury. Jejími dalšími specializacemi, kromě programu, by pak ještě pravděpodobně byl například pojem Administrativa.

### Událost
Istancemi této třídy jsou například konkrétní schůzky a výpravy, pořádané během roku, ale i tábory a další akce přes léto. 
To implikuje, že každá z instancí této třídy má stanovený nějaký specifický termín svého pořádání. 
Ve skutečnosti to typicky bývá konkrétní čas začátku a alespoň přibližný čas návratu (ukončení akce). 
Pojem "akce" je zde použit jako rovnocený k události, nicméně je možné, že Událost je specializací Akce, jakožto obecnějšího pojmu. V každém případě by. mělo být možné označovat událost za akci. 
Klíčovou charakteristikou událostí je, že průběh každé z nich, i "jen" dvouhodinové schůzky, se skládá z jednotlivých Programů. Tedy alespoň se to tak říká hovorovým označením. Jelikož byl Program určen jako nejobecnější pojem v modelované doméně, samo toto tvrení o složení (částech) události přílišno výpovědní hodnotu sice nemá. Avšak je tím implikováno, že události by měly být asociovány s nějakou třídou, která je zahrnuta mezi specializacemi pojmu Program.

### Aktivita
Třída Aktivita - reprezentuje entity, které samy, narozdíl od událostí, nemají specifikován žádný konkrétní termín jejich pořádání. 
Instance třídy Aktivita představují totiž soubory znalostí určené ke znovuvyužívání, postupnému obohacování a zkvalitňování pořádaných událostí. 
Jestli je možné pomocí zdokonalení známých aktivit dosáhnout kvalitnějších událostí, naznačuje to že by mezi aktivitou a událostí měl být modelovaný vztah. Tento vztah pak skutečně existuje. Pro pojmenování rolí v tomto vztahu bylo využito pojmu, používaného primárně v rámci pořádání táborů, kdy každý den je rozdělen na jednotlivé "bloky", neboli bloky programu, které představují hlavní stavební prvky táborového dne. 
Jelikož pak tábor představuje Událost a jednotlivé takzvané bloky, jsou prakticky jen instance třídy Aktivita na jejichž přípravu bylo vynaloženo typicky více úsilí než na běžné programy, je možné využít označené role aktivity "programový blok" a role události pak 'realizátor bloku'. S tím, že obě strany vztahu mohou být zastoupeny žádným, ale i několika instancemi z koncových tříd.
### Hra
Třída Hra je speciálním případem aktivity, to znamená, že události mohou jako bloky využívat i instance her, protože jsou zároveň také aktivitami. 
Jak se hra liší od aktivity, či jaké může mít hra další vztahy, je popsáno v následujících částech práce. Není zde tedy rozváděna do větších podrobnosti.

## Rozšíření základních tříd
### Program
model
 ![[Program-SystematickyTvořenýDiagramTříd.jpg]]
Ke třídě Program byly pojmy vybrány, ve všech připadech kromě zpětné vazby, z báze chystam program.

Nalezení první skupinky podobných pojmů nebylo obtížné nalézt, jelikož chystamprogram dělí aktivity podle 'OblastRozvoje' a dále podle podoblastí každé z oblastí. V modelu je proto každá z oblastí modelována jako samostatná třída obsahující její přípustné hodnoty a připojená ke třídě 'OblastRozvoje' jako její specializace. Tato notace vychází z takzvaných číselníků neboli enumerates v UML, pomocí kterých jsou reprezentovány atributy, které mohou nabývat pouze hodnot z předdefinované sady.

Následně byla identifikovány i 'VýchovnýCíl' a 'NapojeníNaStezku' jako specializace ze stejné sady jako 'OblastRozvoje', bylo tak učiněno proto že všechny ze tříd představují z hlediska programu jeho zaměření, něco čeho se autor programu snažil jeho prostřednictvím dosáhnout. Byla proto vymodelována třída 'CílProgramu', která tyto různá zaměření sdružuje.

Alternativně by se daly vztahy znázornit ke každé ze specializací zvlášť, ale použitá varianta je vhodnější pro případy, kdy je šance, že specializací v této sadě může potenciálně být i více než je v aktuálním modelu zachyceno. Program může být například zacílen i na dosažení určitého milníku v dlouhodobé hře, nebo na specifickou dovednost, kterou by děti při jeho pořádání měly zapojit a tím si je tak procvičit. Třída reprezentující tyto pojmy by pak mohla být pojmenována jako OddílovéCíle a sdružovala by rozličné specifičtější zaměření, která oddíl společně vyhodnotí jako relevantní, ale nejsou konkretně adresovany oficiální literaturou.

Mezi zbývajicemi třídami se dále nepodařila identiti žádná další skupinka tříd s podobnými názvy u kterých by dávalo smysl je generalizovat Sice si blízké, ale nezaměnitelné jsou dvojice tříd zdroj-Příloha, reflexe-Zpetná vazba. V obou případech jsou však obě třídy, k té základní, asociovány z jiných důvodů.

Zdroj značí materiály využité Při tvorbě daného programu a přílohy jsou zamýšlené na využití při pořádání. Reflexe znázorňuje představu autora o tom které části programu by po provedení měly být disku­továny a tvořit tak podněty pro sbíranou zpětnou vazbu. Asociativní vztah je proto modelován jak mezi oběmi temito třídami i pak od každé zvlášt ke třídě Program. Symbolický rámec pak představuje témata a tématické celky, jenž dětem ozvláštňují běžné úkony a usnadňují si zapamatovat lépe informace, které se během programu dozvěděly. [ ]

Jako jediné třídy, které jsou asociované se většinou instancí třídy Program nakonec byly vyhodnoceny pouze Název, Anotace (Popis) a Obsah hry, jenž tvoří dále nespecifikovaný prostor, do kterého mají být zapsány všechny jinde nezařazene informace potřebné či hodící se při provedení daného programu.

 
### Aktivita
model
 ![[aktivita-SystematickyTvořenýDiagramTříd.jpg]]
 K základní třídě aktivita byly kromě zbývajících pojmů z báze chystamprogram přidány ještě pojmy 'VěkNejmladšího' a 'VěkNejstaršího', které se původně nacházely v encyklopedii.

Kromě těchto dvou zmiňovala encyklopedie také pomůcky a materiál, velikost skupiny, místo konání, věk skupiny a dobu trvání.

Generalizovaná třída byla v tomto případě vytvořena pouze jedna. Je využita ke sjednocení dvou možných variant zaznamenání věku skupiny (buď pomocí definování spodní a vrchní hranice pro věk hráče nebo pomocí opět číselníků s předdefinovanými hodnotami, pro jednotlivé věkové kategorie.

Spolu s generalizovanou třídou věku skupiny je k aktivitám přiřazena ještě třída velikost skupiny která je rovněž reprezentována m výčtem přípustných hodnot.

Jelikož obě třídy představují charakteristiku skupiny pro níž je program zamýšlen, když spojenej pomocí nové názvem cílová skupina. A opět stejně jako v případě věku skupiny je zde využito kompozice namísto generalizace, jelikož věk skupiny i velikost mají  pro instance třídy Aktivita podstatně odlišné význam.

Obdobně bylo provedeno pro třídy 'DobaTrvání' a 'DobaNaPřípravu' stejně jako psychická a fyzická náročnost.

Asociačním vztahem byly připojeny pouze třídy poznámek. Jelikož oproti například třídám Trvání nebo Náročnost, jsou poznámky uvedeny pouze u menší částí z nich

Ostatní třídy mají jako datový typ (přípustné hodnoty) buď samotné číslo nebo sadu přípustných hodnot, takže je možné jich relativně bezúsilné zaznamenávání, narozdíl od třeba metodických poznámek. Navíc tyto numerické a kategorické proměnné představují jeden z nejrelevantnějších atributů, při přípravě nových programů a hledání inspirace, podle kterých je možné si snadno a celkem přesně zúžit prohledávané varianty. V důsledku těchto faktorů bývají tyto atributy uvedeny u většiny zaznamenaných aktivit, proto byly ke třídě 'Aktivita' připojeny jako jí vlastní atributy.


### hra
model
 ![[hra-SystematickyTvořenýDiagramTříd.jpg]]
Mezi zbylými pojmy z encyklopedie her identifikovány 3 hlavní skupiny podobných termínů.

První skupinou jsou jednoduché pojmy prezentovatelné binární hodnotou (ano, ne), které zároveň přímo charakterizují přiřazené instance her. Tyto pojmy byly proto modelovány jako atributy třídy 'Hra'.

Druhou skupinou představovaly pojmy, jenž jsou instancemi her využívány proto byly sjednoceny generalizovanou třídou 'NástrojHry'. Nicméně i tak se mezi všemi specializovanými nástroji her stále nacházely tři podstatně odlišné celky, těm byla proto přidána další úroveň generalizace, která je tvořena třídami 'AudiovizuálníNástrojHry', 'PravidloHry' a 'MechanikaHry'.

Pravidla přitom představují omezení, jenž jsou hráčům stanovena a v jejichž vymezení by se měli pohybovat. Zatímco mechaniky jsou prostředky, které jsou hráčům poskytnuty, aby je v rámci hry mohli využívat.

Poslední skupinou jsou pak vlastnosti a schopnosti, které se při hře projevují nebo uplatňují,  v této skupině je však obtížné najít smysluplnou generalizaci. Na první pohled se totiž všechny jeví jako lidské rysy (PovahovéVlastnosti, DuševníSchopnosti, TělesnéVlastnostiASchopnosti, bylo by proto teoreticky možné sloučit je pomocí atributů v nově vytvořené třídě. Jedná se však jen o tři podstatně odlišné celky a není pravděpodobné přidání dalšího podobného výčtu, jelikož už tento je poměrně dost obsáhly a na první pohled dost kompletní co se zahrnutých hodnot týče, bylo proto pro zachování sémanticky přesného modeluproto rozhodnuto, připojit  každou z těchto tříd separátně.

A protože většina her by měla nějakým způsobem rozvíje alespoň nějaké z těchto vlastností a schopností, jsou tyto připojeny  opět jako atributy vlastněné třídou 'Hra'.

Třída 'DokumentárníFotografie' je v původní literatuře zmiňována v souvislosti s pojmem 'CharakteristickýOkamžik', proto i v tomto modelu je asociována stejně.

Co se třídy 'PrvekZahrnutýVeHře' týče, její přípustné hodnoty se sice zdají být velmi významově blízko třídám, které byly generalizovány jako mechaniky, avšak třída hrou zahrnutých prvků byla ponechána odděleně. Rozhodnutí bylo učiněno proto, že narozdíl od mechanik jako rozpočítadlo, které může mít i relativně komplexní význam, alespoň vzhledem k pojmům jako běh, zpěv nebo dialog. Pro tyto, dalo by se říct primitivní typy, se zdá použitý výraz 'Prvek' býti výstižnějším.

 
### událost
model
 ![[udalost-SystematickyTvořenýDiagramTříd.jpg]]
Událost, jakožto pojem z nejméně obsáhlé a zároveň i nejméně prohledávané báze, k sobě má přiřazeno jen úplné minimum pojmů, poskytujících pouze základní reprezentaci dané třídy a tak možnost jí zohlednit v modelu.

Byla definována základní klasifikace událostí na schůzky, výpravy a tábory. S tím, že instance třídy Událost mívají typicky určený začátek a konec ve formátu dne a hodin a k tomu i konkrétní místo, kde se budou odehrávat (hodnoty reprezentované pojmem místo v kontextu události se liší od hodnot místaKonání u aktivit).

## ~~-! kdyžtak ven| Porovnání s alternativním pohledem na skutečnost~~
### -Modely
Systematický
 ![[SystematickyTvořenýDiagramTříd.svg]]
NEsystematický
 ![[NEsystematickyTvořenýDiagramTříd.jpg]]
### !Porovnání
Stejný název
+stejné vlastnosti (properties, relationships)


# !!!!! | Schema databáze
## !!! | Návrh schématu
### Program (transformed)
![[program-GraphSchema.jpg]]

### Událost (transformed)
![[udalost-GraphSchema.jpg]]

### Aktivita (transformed)
![[aktivita-GraphSchema.jpg]]

### Hra (transformed)
![[hra-GraphSchema.jpg]]

## !! | Ověření kompetencí navrženého schématu
### !Vzorová data = kolik správných výsledků pro jednotlivé kompetenční otázky obsahují



### !Vzorová queries = Cypher query + počet nalezených výsledků 
odpovídající kompetencím existujících bází

