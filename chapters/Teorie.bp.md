---
aliases: 
up:
  - "[[../README|README]]"
---

# Získání infrastruktury vyhovující požadavkům práce
V této kapitole budou prezentovány výsledky z výběru softwaru, který by umožňil návrh báze odpovídající podmínkam stanovených v cíli této práce.
## Výběr zdrojů k analýze (sw)
### Vyhodnocení hlediska zápisu pro všechny kandidáty %% fold %% 
Vyhodnocení tohoto hlediska je velmi přímočaré. Vzhledem k tomu, že tento návrh klade velký důraz na minimalizaci nových nároků na uživatele. Zejména pak na nároky pro zapisování, jelikož pro navrhovanou bázi je klíčové, aby do báze uživatelé zapisovali a sdíleli tak své zkušenosti z připravených programů, čímž budou obohacovat prohledatelný obsah. Proto z tohoto hlediska budou vyřazeni kandidáti, kteří umožňují zapisování obsahu jen pomocí specifického jazyka.
Jak bylo řečeno v metodice, ani jeden z produktů společnosti Google toto kritérium nesplňuje, zůstávají tedy jako přijatelné pro návrh. Oproti tomu, ani jedna z databází přes toto kritérium neprojde. Pro interakci s databází MySQL je totiž potřeba využít SQL (Structured Query Language) a v případě Neo4j se jedná prozměnu o 'Cypher', což je také jazyk, akorát uzpůsobený k prohledávání grafových struktur.
#### přijatelné pro zápis
- gDocs
- gSheets
### Vyhodnocení hlediska čtení pro všechny kandidáty %% fold %% 

Vyhodnocení druhého hlediska však bude již komplexnější, konkrétně tak, že pro získání výsledků využívá vícero kritérií, která jsou na závěr agragována do jednoho souhrnného vyhodnocení.
#### rychlost
První kritérium se zaměřuje na rychlost získání výsledků. 
Při následujícím hodnocení kandidátů nebude mít podstatnou roli. Nicméně nedostatečná rychlost vyhledávání v záznamech, pokud je možné jen manuální otevírání jednotlivých dokumentů podle jejich názvu a umístnění ve složce, je primárním důvodem vzniku této práce. A proto není možnost manuálního prohledávání ani začleněna mezi kandidáty, kteří všichni toto kritérium splňují.
#### správnost
Další kritérium, absence chyb jak prvního, tak druhého typu, je však již relevantním pro hodnocené kandidáty. 
Nejsnazší vyhodnocení tohoto kritéria umožňují kandidáti databázového typu, v jejich případě je totiž tato podmínka zahrnuta již v jejich podstatě jako databázích. Proto u nich absence chyb při vyhledávání nebude dále ověřována a bude předpokládáno, že toto kritérium splňují.
Pro vyhodnocení bezchybného vyhledávání v gSheets bude posuzována vestavěná funkce 'query', která nabízí podobné možnosti prohledávání tabulek v daném dokumentu gSheets, jako relační databáze svým SQL. Jelikož se tedy jedná opět o prohledávání přesně strukturovaných dat, pomocí exaktního algoritmu, bude předpokládáno, že tato funkce operuje bezchybně.
Pro hodnocení vyhledávání v gDocs by mohla být využita funkce 'Najít' rozšiřitelná na 'Najít a nahradit'. Ta nicméně funguje pouze v rámci jednoho dokumentu. Což vzhledem k tomu, že by navrhovaná báze měla být v rámci škálovatelnosti rozdělena do více dokumentů připadně na sebe odkazujících, nedělá z funkce 'Najít' vhodný způsob k hodnocení. Na základě předpokladu, že by báze neměla být zapsána v jediném dokumentu, ale spíše rozdělena do více dokumentů, bude k vyhodnocení kritéria bezchybného prohledání u gDocs využita funkcionalita prohledávání služby gDrive. Prakticky se jedná o prohlédávání obsahu na disku pomocí vyhledávacího řádku na vrchu webového grafického rozhraní služby gDrive. Ten nabízí, mimo možnosti vyhledávat podle názvu a typu souboru, i možnost zobrazit pouze ty dokumenty, které obsahují konkrétní slovo. Právě tato poslední možnost, vyhledávání dokumentů na základě textu v nich obsažených, bude hodnocena podle kriteria bezchybnosti vyhledávání. 
Toto hodnocení bude provedeno pomocí krátkého experimentu, jenž se bude skládat z vyzkoušení dvou případů. 
1. Zapsání klíčového slova "test::" do nového dokumentu a následný pokus o vyhledání dokumentů podle toho zda obsahují klíčové slovo.
Aby byla zohledněna možnost, že systému trvá nějakou dobu, než provede indexování nově vytvořených dokumentů a umožní tak vyhledávání v nich. Bude vyzkoušena ještě následující situace.
2. Vybrání co nejunikátnějšího klíčového textu z libovolného souboru zapsanáho na mém disku déle než měsíc, následované pokusem o nelezení daného souboru podle toho, že obsahuje vybraný klíčový text.
Z výsledků těchto dvou experimentů vyplynulo, že tato varianta prohledávání jednoznačně není bezchybná. Jelikož oba pokusy o vyhledání dokumentu obsahujícího klíčový text byly neúspěšné, byly sice rychlé, avšak dokument z něhož byl získán klíčový text použitý k hledání, nebyl zobrazen ani v jednom případě. Postupujícími sw kandidáty k dalšímu  hodnocení jsou tedy pouze gSheets a databáze MySQL a Neo4j. gDocs byly na základě experimentálně zjištěných výsledků vyhodnoceny jako nástroj nepřijatelný pro uživatelské rozhraní zprostředkující čtení obsahu navrhované báze.
#### příjemnost
Kritérium příjemnosti je ze všech kriterií zatím nejkomplexnější, proto i jeho vyhodnocení bude tomu odpovídat. Jak bylo stanoveno v metodice, bude nejprve vyhodnoceno pořadí zbývajících kandidátů podle každého z dílčích kriterií zvlášť. A tak získané dílčí výsledky budou následně využity k výběru nejvhodnějšího z kandidátů z hlediska příjemnosti prohledávání obsahu navrhované báze.
Následující dílčí kriteria budou vyhodnocena pro gSheets (funkce 'query'), MySQL (SQL) a Neo4j (Cypher). Využito bude primárně odhadů a dedukce.
1. počet znaků potřebných k napsání dotazu
Při hodnocení tohoto dílčího kritéria, je vycházeno z předpokladu, že funkce gSheets 'query', jakožto pouhá napodobenina funkcionality nabízené 'SQL', bude v případně jednoduchých dotazů možná i stejně úsporná na potřebné znaky jako jako SQL pro obdobný dotaz. Pro komplexnější dotazy, vyžadující například data z víc tabulek, je potom předpokládano, že SQL bude, ve srovnání s funkcí query v gSheets, umožňovat díky své podstatně rozvinutější funkcionalitě způsob zapsání daného komplexnějšího dotazu s nižším počtem znaků, než funkce query. 
Pro porovnání počtu znaků vyžadovaných k napsání dotazu bázi Neo4j a MySQL je využito článku s názven 'Use graph databases for complex hierarchies' [ ]. Tento článek na modelovém příkladu dat, vyhodnocuje několik různých dotazů a porovnává jejich zápis a následný postup vyhodnocení v případě využití SQL oproti případu s využitím jazyka Cypher. V této práci jsou však zohledněny pouze porovnání zapsaných dotazů, nikoliv způsoby jejich vyhodnocování.
Z výsledků prezentovaných v článku vyplývá, že pro zapsání SQL dotazu je téměř v každém případě potřeba více znaků, než pro získání stejných výsledků pomocí jazyka Cypher. SQL přitom v některých případech vyžaduje až několikanásobně více znaku než ekvivalent zapsaný Cypherem. Proto navíc tato práce předpokládá i to, že ani pomocí funkce query v gSheets, není možné dosáhnout kratšího zápisu dotazů, než v případě Neo4j a Cypheru, jelikož odhadovaný počet znaků vyžadovaný funkcí query je v jednoduších případech podobný jako v případě SQL a ve složitějších situacích horší než SQL.
Výsledné pořadí tohoto dílčího kriteria proto je:
	1. místo - Cypher
	2. místo - SQL
	3. místo - =query()

2. Nabízí v základu webové GUI?
Pro vyhodnocení druhého dílčího kriteria není třaba se uchylovat k odhadům, jelikož kandidáti buď budou nabízet možnost webového GUI v základní instalaci, nebo nebudou. Určení této binární hodnoty pro kandidáty, bude provedeno prohledáním internetových zdrojů s dotazem například "MySQL web GUI". A na základě nalezených výsledků bude určeno zda daný kandidát úspěšně splní toto kriterium.
Pro gSheets bylo vyhodnoceno, vzhledem k podstatě nástroje jako na cloudu založené služby, že vskutku nabízí ve svých základních možnostech zobrazení grafického rozhraní v prostředí prohlížeče, bez nutnosti lokální instalace čehokoliv jiného než samotného prohlížeče.
Pro MySQL z hledání vyplynulo, že grafická rozhraní umožňující přístup k této bázi jsou typicky povahy lokální instalace. Rovněž však existují i možnosti jako myPhpAdmin [ ], který je zdarma a nabízí webové GUI. Nicméně všechny z těchto variant jsou dodatečné nástroje, z nichž by bylo potřeba provést patřičný výběr, kdyby byly návrhem uvažovány jako možnosti. Jelikož tedy žadné, v základní instalaci zahrnuté webové GUI není pro MySQL k dispozici, znamená to pro relační databázi podle tohoto kriteria druhé a zároveň poslední místo.
Pro Neo4j naopak bylo velmi snadné najít nástroj 'Neo4j Browser', jelikož to byl první výsledek po zadání dotazu "Neo4j web gui". Jednalo se o odkaz na oficiální dokumentaci Neo4j, kde bylo řečeno, že se jedná o výchozí rozhraní pro interakci s databází a zároveň je zahrnuto ve výchozí instalaci [[myDM/Zotero/LiteratureNotes/Neo4jBrowserDocsHomepage#^HBZ4U6B9aKFRES7KJ]].
Výsledné pořadí tohoto dílčího kriteria proto je:
	1. místo - gSheets, Neo4j
	2. místo - MySQL


Finální pořadí kandidátů podle kriteria příjemnosti čtení jejich obsahu je proto následující.
	1. místo - Neo4j (1+1)
	2. místo - gSheets (1+3), MySQL (2+2)
A kandidátem vybraným v rámci hlediska čtení zapsaného obsahu se tak stává databáza Neo4j, jelikož umožňuje interakci pomocí dotazů s nejnižším počtem znaků z posuzovaných kandidátů a zároveň k interakci s ní není třeba žádný dodatečný software, který by nebyl zahrnut v základní instalaci.
## Výsledky analýzy obsahu (sw) %% fold %% 
Vybraným softwarem pro základ navrhované báze jsou tedy gDocs a gSheets jako uživatelské rozhraní pro zapisování údaje do báze a případnou modifikaci zapsaných údajů. Spolu s databází Neo4j sloužící jako uživatelské rozhraní k prohledávání zapsaných údajů v navrhované bazi skautských programů. V této části boudou představeny datové struktury využívané jednotlivými vybranými nástroji spolu s představením jejich možností vzájemné integrace.
### datové struktury (uložení)
#### gWorkspace
Oba tyto nástroje z prostředí gWorkspace (gDocs, gSheets) mají jeden aspekt své struktury shodný. A to sice ten že v obou případech se jedná o soubory, uložené na disku google (gDrive). Každý ze souborů pak má přiřazené unikátní id, které je mimochodem součástí webové adresy (url) využité pro zobrazení GUI editoru daného souboru. Pokud tedy v prohlížeči bude otevřen jeden konkrétní soubor tabulek z disku s identifikátorem ID, url zobrazované ve vyhledávacím řádku prohlížeče bude `https://docs.google.com/spreadsheets/d/{ID}/edit#gid=0` []. Adresa funguje i v případě vynechání textu za posledním lomítkem, i v případě že je text "spreadsheets" nahrazen textem "docs" a je použito ID náležící dokumentu místo tabulek. Kromě id má také každý soubor přiřazený název, typ (gdocs,gsheets,pdf,...) a další. Navíc může být přiřazen například popis, který se zobrazuje v GUI gDrive i gDocs, ale i další volitelné atributy se kterými je však možno interagovat jen pomocí REST API [ ]. 

Vnitřní strukturu souborů už však mají oba nástroje specifickou. 
V případě dokumentů, je každý tvořen například záhlavím, zápatím a tělem dokumentu (nejedná se o kompletní výčet) [ ]. Tělo dokumentu je pak dále členěno na jednotlivé elementy. V praksi je elementem každý nový řádek vytvořený stisknutím klávesy 'enter', případně vložený objekt jako třeba tabulka, nebo obrázek. Každý elemant pak může mít přířazené hodnoty reprezentující jeho formátování, ale i konkrétní text zapsaný v daném elementu. Navíc, protože pro dokumenty je důležité pořadí zapsaných elementů, je s každým elementem asociován i identifikátor vyjadřující pořadí daného elementu v rámci těla dokumentu [ ]. Je tak například možné získat na jakých pozicích, z hlediska pořadí v dokumentu, jsou nadpisy úrovně 1 a pomocí jednoduchých aritmetických operací získat na jakých pozicích v dokumentu začíná i končí elementy pod konkrétním nadpisem 1. urovně.

V případě tabulek, jsou jednotlivé soubory organizovány do listů (stránek), s tím že každý list je tvořen tabulkovou strukturou ve které může být zapsáno i více tabulek. Konkrétní rozsahy v rámci listů mohou být také pojménovány a reference na ně tak mohou být realizovány pomocí tohoto pojmenování [ ]. Jelikož se však jedná spíše o sekundární rozhraní pro navrhovanou bázi, které je zamýšleno zejména na zapisování dalo by se říci konfiguračních údajů (dostupné materiály, seznam členů, výchovné cíle), popis struktury jeho souborů není rozebírán do větších podrobností.
#### Neo4j
Neo4j, vzhledem ke své podstatě databáze, má strukturu uložených údajů značně odlišnou. Struktura označovaná jako 'property graph' využitá Neo4j k uložení zapsaných dat, je na disku realizována pomocí několika odlišných souborů. To konkrétně znamená, že každá část uložené grafové struktury (nodes-vrcholy, relationships-vztahy, lables-popisky/štítky, properties-vlastnosti) je uložena v separátním souboru [ ].
Všechny tyto čtyři soubory se přitom skládají ze záznamů o fixní délce bytů, dalo by se na ně tedy pohlížet jako na tabulky, ve kterých je možné velmi rychle přistupovat ke konkrétním záznamům, pokud známe pořadí ve kterém byly do souboru zapsány. Právě proto je databází využita tato fixní struktura, jelikož je s jeji pomocí je možné efektivní propojení jednotlivých částí napříč čtyřmi separátními soubory. Například pokud je k vrcholu přiřazená vlastnost, bude ve vyhrazeném místě (bytech) pro zaznamenání přiřazených vlastností v daném záznamu v souboru vrcholů uvedeno pořadí ve kterém byla přiřazená vlastnost zapsána do souboru obsahujícího vlastnosti. Dalo by se tak říci, že pořadí zápisu jednotlivých záznamů do souborů, představují primární klíče pro jednotlivé "tabulky" a zachycení grafové struktury je dosaženo pomocí zápisu těchto klíčů k ostatním souvisejícím částem jako cizích klíčů. 

Dále jsou v knize "Graph databases" od vydavatelství OReilly popsány i konkrétní struktury jednotlivých souborů. V rámci představení struktury databáze, jsou proto představeny i tato specifika. Popsaná struktura záznamu v souboru ukládajícím vrcholy je následující [ ]. 
- byte 1 - (in-use flag) Slouží bázi k určení, zda je daný záznam používaný, či zda může být smazán a jeho pozice tak uvolněna.
- bytes 2-5 - Reprezentují identifikátor prvního připojeného vztahu (odkaz realizovaný pořadím záznamu v souboru vtahů).
- bytes 6-9 - Reprezentují identifikátor první připojené vlastnosti (odkaz realizovaný pořadím záznamu v souboru vlastností). 
- bytes 10-14 - Reprezentují odkazy na přiřazené 'lables', případně konkrétní štítky/popisky, pokud jich je přiřazeno pouze nízké množství.
- byte 15 - Rezervován pro budoucí využití.
Jak je řečeno v knize, jedná se tak prakticky jen o "hrstku odkazů, odkazujících do seznamů vztahů, popisků a vlastností" [ ].

Pro záznam v souboru ukládajícím vztahy je pak popsána následující struktura [ ].
- byte 1 - (in-use flag) Značící, zda záznam může být smazán a nahrazen novým.
- bytes 2-5 - Identifikátor prvního vrcholu v tomto vztahu. V případě směrovaného vztahu je tento vrchol počátkem.
- 6-9 - Identifikátor druhého druhého vrcholu v tomto vztahu. V případě směřovaného vztahu je toto koncový vrchol.
- 10-13 - Identifikátor typu vztahu, který odkazuje na soubor obsahujícím seznam všech typů vztahů v databázi použitých.
- 14-17 - Identifikátor předchozího vztahu počátečního vrcholu.
- 18-21 - Indetifiátor následujícího vztahu počátečního vrcholu
- 22-25 - Identifikátor předchozího vztahu koncového vrcholu
- 26-29 - Identifikátor následujícího vztahu koncového vrcholu
- 30-33 - Identifikátor první připojené vlstnosti.
- 34 - První v řetězu vztahů?

Vlastnosti (properties) jsou potom uloženy následujícím způsobem. Opět je využita fixní velikost pro jednotlivé záznamy. S tím že každý záznam vlastnosti obsahuje odkaz na další související záznam. To je z důvodu, že vzhledem k fixní velikosti uložených vrcholů a vztahů, jsou k těmto částem grafu zaznamenány pouze odkazy na první přiřazenou vlastnost, a ostatní přiřazené vlastnosti jsou pak připojeny právě pomocí odkazu na následující záznam vlastnosti obsažený v záznamu první přířazené vlastnosti k vrcholu, či vztahu. Podobný princip je pak aplikován i při procházení všech ostatních prvků v zaznamenaném grafu. Kromě tedy odkazu na další záznam v tomto 'řetězu vlastností', je u každého záznamu uveden datový typ dané vlastnosti (jakýkoliv primitivní typ podporováný Java Virtual Machine, strings, arrays JVM primitivních typů), spolu s odkazem na soubor 'indexu vlastností', který obsahuje jména vlastností použitých v bázi. A na závěr je u každého záznamu vlastnosti buď uložena samotná hodnota vlastnosti, pokud je dostatečně malá, aby se vešla do fixně velkého záznamu. Nebo v případě, že velikost hodnoty přesahuje velikost místa poskytnutého záznamem fixní velikosti, je uložen pouze odkaz na zapsanou hodnotu vlastnosti, a samotná hodnota je uložená do speciálního dynamického uložiště vlastností, které je realizováno opět samostatným souborem. Ve skutečnosti Neo4j disponuje dvěma těmito dynamickými uložišti. První je optimalizováno pro uložení delších textů (stringů) a podporuje například full-text indexování a následné prohledávání těchto textů podle obsaženého textu. A druhé optimalizované pro uložení delších polí (arrays), typicky ubsahujících čísla, v oblasti strojového učení a neuro sítí také označovány jako vektory, nebo tensory [ ]. 

Toto dynamické uložiště polí proto může být využito například pro uložení takzvaných 'embedded' hodnot, která jsou získány "zakódováním" nějakého vstupu (text, obrázek,...) pomocí AI modelu. Takto získané hodnoty se následně využívají k 'Retrieve Augmented Genaration', což prakticky znamená proces, ve kterém jsou nejdříve vyhledány záznamy, jejichž 'embedded' hodnota je vektorově podobná 'embedded' hodnotě uživatelem zadaného dotazu. Z nalezených vektorově podobných záznamů je následně vybráno vrchních x, a ty jsou poskytnuty některému z jazykových modelů spolu s uživatelovým dotazem, aby na základě takto obohacených podkladů teprve vygeneroval odpověď zobrazenou nakonec uživateli.
### integrovatelnost (přístup)
#### gWorkspace
Interakci s vybranými nástroji z gWorkspace pomocí programového kódů zprostředkovává googlem provozované REST 
API, to umožňuje pomocí http dotazů jak získávání obsahu jednotlivých dokumentů, tak i modifikaci jejich obsahu. Pro použití tohoto API je však potřeba každý dotaz adekvátně autorizovat [ ]. Existuje nicméně ještě jedna možnost interakce s dokumenty pomocí kódu, která ale nevyžaduje explicitně autorizovat každý dotaz. Jedná se o interakci se službami v rámci gWorkspace pomocí služby google Apps Scripts, která je rovněž zahrnuta v gWorkspace. Samotné Apps Scripts představují službu, která umožňuje napsání téměř libovolného javascript kódů a jeho spouštění v rámci definovaných limitů zdarma. Scripty mohou být spouštěny buď časovačem, nebo přes "zavolání" url adresy přiřazené automaticky implementaci daného kódu napsaného v Apps Scripts. Hlavní výhodou při použití Apps Scripts je to, že rozhraní ostatních služeb (gDocs, gSheets, gDrive,..) není potřeba volat pomocí REST API a http dotazů, ale stačí rozhraní dané služby přidat jako knihovnu ke psanému scriptu. Jedinkrát při prvním spuštění je třeba odsouhlasit, že jako majitel účtu souhlasíte s tím, aby daný script měl přístup k vybrané službě, a tím starosti s autorizací požadavků končí [ ]. Kromě denního limitu na počet spuštění, je bezplatné využití této služby vykoupeno ještě jedním podstatným omezením. A to sice, že není možné provádět "volání ven" ze skriptu (externí komunikaci) jinak než s využitím předdefinované funkce 'UrlFetch()'. Což zároveň znamená, že i pokud se podaří dostat do skriptu knihovnu například pro komunikaci s databází nebude tato knihovna fungovat [ ].
#### Neo4j 
Možnosti programové interakce s databází Neo4j závisí na tom, která z implementací je využita. První varianta implementace Neo4j je cloud verze nabízená jako SaaS, spolu s poměrně dostatečným objemem zdrojů v rámci bezplatné úrovně účtu. Tato verze nicméně umožňuje programovou interakci, pouze pomocí knihoven, které jsou sice pro většinu nejběžnějších jazyků k dispozici, takže ve většině případů bude tato varianta nabízet dostatečnou konektivitu. Avšak v případě, jako dříve zmíněné Apps Scripts, které omezují možnosti externí komunikace pouze na http dotazy skrze předdefinovanou funkci, představuje absence podpory http komunikace v cloudové verzi Neo4j poměrně problém. Naštěstí existuje druhá varianta implementace, konkrétně takzvaná 'self-hosted' varianta, která může být například s využitím dockeru, nebo pomocí klasické instalace spůštěna na libovolné výpočetní instanci (počítači). A tato 'self-hosted' varianta umožňuje jak programovou interakci pomocí http tak pomocí knihoven pro konkrétní jazyky.
## Vyhodnocení výsledků analýzy (sw) %% fold %% 
Jak bylo stanoveno v metodice, v rámci této části bude popsán způsob implementace navrhované báze, který by nevyžadoval víc prostředků na údružbu, než sám ušetří. Konkrétně, vzhledem k tomu, že aktuálně není k dispozici způsob jak změřit ušetřený čas při využívání báze, je vycházeno z předpokladu, že pokud budou vyžadovány lidské, či finanční prostředky na to, aby byla prováděna jednosměrná synchronizace zapsaného obsahu v gDocs do efektivně prohledatelné databáze, nebude ušetřený čas větší, než ten vyžadovaný na údržbu. Proto bude popsána možnost automatizace synchronizačního procesu taková, která by nevyžadovala finanční prostředky na svůj provoz. Rovněž budou definovány konkrétní funkcionality, na kterých závisí proveditelnost popsaného způsobu.
- [ ] DODĚLAT [chap::teorie] [sect::interpretace.sw] CRITICAL [treq::180] [weig::8]
Na základě vybraných kandidátů a jim dostupných možností bylo určeno
### automatizace jednosměrné synchronizace (zrcadlení)

### nasazení databáze

### funkcionality k ověření

# Získání pojmů asociovaných se skautských programů
## !-Hodnocení zdrojů
### chystamprogram
 - [ ] UČESAT [chap::teorie] [sect::hodnocení.chystamprogram]

"""
Její předností je zaměření na výchovnou a rozvojovou hodnotu programů. To je především zprostředkováno díky možnosti zapisovat k jednotlivým programům jejich výchovný cíl. Ale také možností zapisovat, na který bod ve Stezce je program napojen. Což je dobré a užitečné proto, že Stezka nepředstavuje jen rámec pro děti, podle kterého by se mohly samy všestranně rozvíjet. Rovně ale jako pomůcka pro vedoucí, když připravují vhodný program pro nadcházející schůzku například. [[myDM/Zotero/LiteratureNotes/StezkyCestickyVlcat#^N5AJVIHJa43Y7SWYU]] 
Drobná nevýhoda však vyplývá z toho, že se jedná o veřejnou bázi za kterou zodpovídá samotná organizace Junák. A to sice, že pro zapsání nového programu, je potřeba být přihlášen skautským účtem ze skautIS a výsledný zápis musí být nejdříve ověřen jejich metodickým týmem. Což sice bude mít pravděpodobně pozitivní vliv na úroveň kvality zaznamenaného obsahu. Nicméně pro sdílení například programu, který je teprve připravován, to tak není vhodné řešení. Jako větší nedostatek však vnímám spíše omezenou možnost poskytování zpětné vazby, a komentářu k zapsaným programům. Jediná možnost hodnocení, je totiž zaslání svého hodnocení pouze soukromě autorovi daného programu. Což opět pro interní využití, které by mělo umožňovat sdílení obsahu a na něm následnou spolupráci, není vyloženě příhodné.
"""
### encyklopedie her
- [ ] UČESAT [chap::teorie] [sect::hodnocení.encyklopedie]

"""
Právě tento objem, pědstavuje hlavní pědnost tohoto zdroje. Jelikož vzhledem k době jeho vydání, existuje šance, že některé zapsané hry, nebudou již dnes pro děti zábavné. Avšak vzhledem ke zmíněnému objemu, by se musela od té doby změnit kompletně celé podstata dětských her, aby tento zdroj již nebyl relevantní, což tato práce nepředpokládá.
S rokem vydání encyklopedie souvisí však i další nevýhody, které přehlédnout nelze. Klíčovým nedostatekm jou značně limitované možnosti efektivního prohledávání, které jsou implicitním důsledkem tištěné formy báze. Hry jsou sice jednotlivými knihami rozděleny podle prostědí do kterého jsou vhodné a dále pak pomocí kapitol. Navíc každá hra má vedle názvu uvedeno specifické značení, popsané na začátků každé z knih, které poskytuje informace například o tom, pro jaký počet, nebo věk hráču je hra vhodná. Nicméně to pořád znamená, že je třeba záznamy procházet manuálně a vizuálně kontrolovat, zda chci o dané hře číst více. Nemluvě o tom, že doplňování zpětné vazby či komentářů rovněž není možné.
""""
### -sdílený disk našeho oddílu
- [ ] DODĚLAT [chap::teorie] [sect::hodnocení.sdílený disk]

## Výsledky analýzy obsahu (báze)

### rešerše obsahu sdíleného disku
Většina dokumentů na sdíleném disku jsou dokumenty využívané pro administrativní účely, nicméně několik složek je dedikováno záznamům o programech. 
První složka pojmenovaná 'Výpravy' obsahuje jeden dokument na jednu výpravu, s tím že zapsaných výprav je přibliženě 40. Jak výpravy souvisí s programem? A co vlastně jsou výpravy? 
Výpravy představují události organizované typicky na jeden, či více dní, kdy vedoucí připravují pro děti nějaký program. Jelikož však i samotná výprava potřebuje přípravu, dá se říci, že samotná událost výpravy je připravovaným programem. Mezi typicky organizované události patří kromě výprav ještě schůzky a tábory. Všechny události přitom mají tu společnou vlastnost, že se skládají z určitých bloků, které mají nějaké naplánované pořadí, to se však může lišit od reálného průběhu události. Jednotlivé bloky pak představují konkrétní aktivity a hry, které jsou při události realizovány.
Druhá složka nese název 'Programy' a obsahuje několik neroztříděných aktivit, které mohou být využity při libovolné připravované události. Navíc jsou zde však i podsložky pojmennované podle jednotlivých věkových skupin (vlčata, skauti), které obsahují popsané aktivity (programy) zamýšlené buď pro mladší, nebo pro starší.
### pojmy získané analýzou
- [ ] DOPLNIT seznam pojmů bez duplicit, formát viz reM [chap::teorie] [sect::pojmy-tabulka]




