
# dotazy na konzultaci co nevyšla
#### Dotazy %% fold %% 
**ověření jako samostatný dílčí cíl? nějaké ověření na výsledky ověření?**
ověření jako oddělená část metodiky?
ověření s metodikou popsanuo u jednotlivých dílčích cílů?

##### ověření 1. dílčího
**? experiment/implementace ?** klíčových prvků pro návrh jako:
- obsah z gDocs je možné číst s pomocí AppsScripts?
- je možné s pomocí AppsScripts přistupovat pouze ke specifickým částem dokumentů na základě jejich absolutního i relativního umístnění ve struktuře dokumentu?
- je s pomocí AppsScripts možné komunikovat s Neo4j?
**Jsou uvedené funkcionality dostatěcným důkazem, že s pomocí AppsScripts je možné dosáhnout zrcadlení aktuálního obsahu gDocs to Neo4j?)**

##### ověření 2. dílčího (analýza bází -> rozšířená definice modelované domény(model))
a) komparace s NEsystematicky vytvořeným modelem
	

b) systematické posouzení správnosti a úplnosti vytvořeného modelu domény skautských programů s využitím LLMs a několika různých promptů
	prompty:
		bez pojmů z bází se zeptat na možné pojmy pro danou doménu
		-||- pro danou doménu s tím, že pojmy budou základem pro databázi, jenž by měla plnit {konkrétní účel popsaný v úvodu}
		popsat dílčí pohledy na model
		nějaké vztahy, které jsou nepravdivé nebo nedávjí smysl (podle LLM)
		které další pojmy by v daném dílčím pohledu mohly být?
		které další pojmy by mohly být v systému, který má  daný {konkrétní účel} (in: pouze seznam pojmů nikoliv celý model (neumí ho přečíst))

##### ověření 3. dílčího (návrh báze)
experiment
1. sestavit a nahrát do DB, vytvořené během ověřování 1. dílčího cíle, ukázkové (demo)  záznamy, získané transformací záznamů z existujících bází tak, aby odpovídaly navrženému schématu. **( Je potřeba nějak *podrobně* komentovat jejitch tvorbu, případně obsah? Nestačí nahrát do veřejného git repozitáře a uvést odkaz?)**
2. sestavit dotazy **(stačí podmnožina, nebo musím všechny? Asi klidně i vyzkouším vśechny, ale jak mám pak výsledky prezentovat? )**


- 


# metodika v2 %% fold %% 
## Metodika analýzy
### ==pojmy asociované se skautskými programy==

#### ==Účel analýzy==
==Cílem této části práce je vybrání pojmů, kteréžto budou představovat odpověď na otázku "Co zaznamenávát v navrhované bázi?"==. ==Abych zjistil jaké informace jsou relevantí pro zaznamenávání v bázi skautských programů, provedu analýzu literatury z této oblasti podle doporučení specifikovaných Bernedtsonem a spol. v jejich knize.
[[myDM/Zotero/LiteratureNotes/berndtssonThesisProjectsGuide2008#^4VZXLNGCaNT5KVCQVp67]]==
![[myDM/Zotero/LiteratureNotes/berndtssonThesisProjectsGuide2008#^TNTKU53KaNT5KVCQVp68]]
Podle autorů je hlavním cílem této metody==, mimo získání konkrétních hledaných údaju, aby čtenář== práce pochopil strategii pro hledání a získání hledaných údajů. Samozřejmě by ==měl také znát a chápat konkrétní důvod proč je analýza prováděna.== 

Duvod k analýze byl již stanoven, proto v následující podkapitole budou nejprve představeny dostupné zdroje, spolu s jejich přednostmi i nevýhodami, ==aby měl čtenář šanci porozumět proč byly, či nybyly vybrány k analýze. A aby čtenář nepochyboval o tom, zda je, vzhledem k cíli práce, analyzováno dostatečné množství zdrojů.== 
V následující podkapitole pak bude popsán konkrétní způsob výběru pojmů z analyzovaných zdrojů, ==aby měl čtenář šanci pochopit jak byly výsledky získány==, proč právě takovým způsobem a ==co získané údaje reprezentují==.
#### ==Analyzované zdroje(báze - ==výběr==+hodnocení)==
==Dostupnou literaturu představují již existující báze, které poslouží zároveň jako inspirace svým obsahem a zároveň jako prostředek pro porovnání možností prohledávání s navrhovanou bází.==
==Co se kvality a vhodnosti pro potřeby práce týče, představují existující báze zcela optimální zdroje k analýze. Navíc vzhledem k tomu, že i rozsah těchto zdrojů je větší, než je vůbec možné v rámci limitovaného rozsahu této práce využít, není prováděno hledání dalších analyzovatelných zdrojů.==

==První z existujících bází je webová stránka 'chystamprogram.skaut.cz', jenž byla vytvořena organizací Junák - český skaut, která zároveň za celý obsah zcela zodpovídá. [[../../myDM/Zotero/LiteratureNotes/ChystamProgramOProjektu#^NMC5UM33aSNYTTS96]] ==

==Její předností je zaměření na výchovnou a rozvojovou hodnotu programů. To je především zprostředkováno díky možnosti zapisovat k jednotlivým programům jejich výchovný cíl. Ale také možností zapisovat, na který bod ve Stezce je program napojen. Což je dobré a užitečné proto, že Stezka nepředstavuje jen rámec pro děti, podle kterého by se mohly samy všestranně rozvíjet. Rovně ale jako pomůcka pro vedoucí, když připravují vhodný program pro nadcházející schůzku například. [[myDM/Zotero/LiteratureNotes/StezkyCestickyVlcat#^N5AJVIHJa43Y7SWYU]] 
Drobná nevýhoda však vyplývá z toho, že se jedná o veřejnou bázi za kterou zodpovídá samotná organizace Junák. A to sice, že pro zapsání nového programu, je potřeba být přihlášen skautským účtem ze skautIS a výsledný zápis musí být nejdříve ověřen jejich metodickým týmem. Což sice bude mít pravděpodobně pozitivní vliv na úroveň kvality zaznamenaného obsahu. Nicméně pro sdílení například programu, který je teprve připravován, to tak není vhodné řešení. Jako větší nedostatek však vnímám spíše omezenou možnost poskytování zpětné vazby, a komentářu k zapsaným programům. Jediná možnost hodnocení, je totiž zaslání svého hodnocení pouze soukromě autorovi daného programu. Což opět pro interní využití, které by mělo umožňovat sdílení obsahu a na něm následnou spolupráci, není vyloženě příhodné.==

==Druhou bázi k analýze pak představuje 'Velká encyklopedie her'. Ta je tvořena čtyřmi samostanými tituly vydanými mezi lety 1987-1988, napsanými panem Milošem Zapletalem. [ ] Jak už název napovídá, jeji zaměření je čistě na hry, které jsou nepochybně také součástí skautských programů, těm se nicméně věnuje velmi podrobně. Slovo "Velká" v názvu totiž nijak zvlášť nepřehání. Každá z knih má v průměru přibližně 600 stran, sice menšího formátu, ale i přesto se často vejdou i dvě hry na stránku.==

==Právě tento objem, pědstavuje hlavní pědnost tohoto zdroje. Jelikož vzhledem k době jeho vydání, existuje šance, že některé zapsané hry, nebudou již dnes pro děti zábavné. Avšak vzhledem ke zmíněnému objemu, by se musela od té doby změnit kompletně celé podstata dětských her, aby tento zdroj již nebyl relevantní, což tato práce nepředpokládá.
S rokem vydání encyklopedie souvisí však i další nevýhody, které přehlédnout nelze. Klíčovým nedostatekm jou značně limitované možnosti efektivního prohledávání, které jsou implicitním důsledkem tištěné formy báze. Hry jsou sice jednotlivými knihami rozděleny podle prostědí do kterého jsou vhodné a dále pak pomocí kapitol. Navíc každá hra má vedle názvu uvedeno specifické značení, popsané na začátků každé z knih, které poskytuje informace například o tom, pro jaký počet, nebo věk hráču je hra vhodná. Nicméně to pořád znamená, že je třeba záznamy procházet manuálně a vizuálně kontrolovat, zda chci o dané hře číst více. Nemluvě o tom, že doplňování zpětné vazby či komentářů rovněž není možné.==

==Za existující bázi by se daly považovat i zápisy ke konkrétním programům na sdíleném disku našeho oddílu. Systematická analýza tohoto zdroje by však byla vzhledem k nesystematicky strukturovaným zápisům poměrně komplikovaná. Avšak pohled na zkoumanou problematiku touto bází je cenný, protože reprezentuje údaje, které jsou pro skautské programy považovány za důležité cílovími uževitali navrhované báze.==
#### ==Analýza vybraných zdrojů (báze)==
==*analýza systematická X extrahování z rešerš*==
==Cílem analýzy těchto dvou zdrojů pak bude pro každý z nich zvlášť, zodpovědét následující dvě otázky.
	- Jaké pojmy jsou využity bází k charakterizování zapsaných aktivit?
	- Podle jakých pojmů umožňuje báze prohledávat? (-> Kompetenční otázky)
Vzhledem k rozdílným strukturám analyzovaných bází, budou odpovědi na otázky v každěm případě získány lehce odlišným způsobem.==

==Nejsnažší zodpovězení umožňuje báze chystamprogam, jelikož poskytuje šablonu pro nové záznamy s pojmenovanými a popsanými políčky(prvky) k vyplnění. 
Odpověd na první otázku je proto získána vypsáním názvů,jejich popisů, případně povolených hodnot pro všechny možné prvky ze šablony. 
K zodpovězení druhé jsou pak prohledýny poskytnuté filtry ve vrchní části stránky 'Hledat Aktivity' v této bázi a vypsány pojmy použité jako názvy parametrů umožňujících filtrování, stejně tak jejich přípustné hodnoty.
-
V případě tištěné encyklopedie je trochu problém, protože zápisy v ní nejsou na první pohled nijak systematicky strukturovány, kromě symbolického značení vedle názvů a svého zařazení do kapitol. Bylo by proto potřeba vybrat vzorek ze záznamů a na základě něj se pokusit určit jaká části se napříč záznamy vyskytují. Naštěstí jedna z encyklopedií zahrnuje ve své Úvodní kapitole část pojmenovanou "Jak zapisovat tradiční hry". Autor se v ní sice věnuje takzvaně tradičním dětským hrám. Tím má na mysli hry, které si děti hrají, ale jejich pravidla existují pouze jako sdílené vědomosti mezi hráči, nejsou však nikde popsána, tudíž je šance, že postupem času tyto hru upadnou v zapomění. Ač se autorova motivace liší od motivace této práce. Výčet parametrů relevantních pro hry, které v této části nabízí. Představuje podobně hodnotný zdroj, jako šablona pro zapisování v předchozí bázi. Pro získání odpovědi na první analytickou otázku proto budou vypsány pojmy právě z tohoto výčtu, nikoliv ze skutečně zapsaných her. 
Co se vyhledávání týče, to je zprostředkováno samotnými knihami, jejich kapitolami a symbolickým značením, u jednotlivých záznamů, popsaným za začátku knih. Proto právě z těchto částí by bylo vhodné získat odpovědi na druhou z analytických otázek. Kapitoly avšak, vzhledem ke značému rozsahu encyklopedie, obsahují příliš mnoho pojmů na to, aby je bylo možné, v rámci limitovaného rozsahu této práce, adekvátně systematicky vyhodnotit a nezanedbat v důsledku toho další klíčové části práce. Proto v rámci analýzy encyklopedie her, k zodpovězení druhé analitické otázky, bude použito pouze symbolické značení u jednotlivých her.==

==Aby bylo možné ve vytvořeném konceptuálním modelu zohlednit i pohled na problematiku očima cílových uživatelů navrhované báze, bude na závěr prezentovaných výsledků ze systematické analýzy prvních dvou bází v teoretické části, doplněna stručná rešerše obsahu uloženého na sdíleném disku. A na základě této rešerše budou identifikovany klíčové pojmy, které by měly být zakomponovány do modelu pojmů.==

#### ==Vyhodnocení výsledků analýzy (báze)==
základní pojmy/třídy
pro každý základní p/t:
	z výsledků vybrat asociovatelné pojmy

### ==infrastruktura vyhovující požadavkům práce==
#### Účel analýzy

Kromě údajů, které by se měly ukládat, je také zásadní otázkou, jak a kde budou záznamy skutečně uloženy. ==Toto rozhodnutí ovlivňuje mimo konceptuální model všechnu další práci.== V této části bude ==určeno právě místo pro uložení záznamů, které by splňovalo podmínky definované cílem této práce a tím tak představovalo odpověď na otázku "Kam uložit záznamy v navrhované bázi?".== 
==Kandidáty na uložiště jsou gDocs jakožto baseline, gSheets jakožto kompromis mezi databází a prostředím dokumentů. Třetím kandidátem je relační databáze MySQL. A nakonec databáze Neo4j jakožto reprezentace NoSQL. Všechny budou vyhodnoceny ze dvou hledisek (zápis, čtení). To znamená, že z jejich vyhodnocení získám dvě sady výsledků.== 
#### ==Výběr zdrojů k analýze(sw)==
##### zápis
Podmínka pro zápis říká, že navržená báze má zachovat úroveň uživatelské zkušenosti, jako poskytuje aktuální řešení. Tím jsou gDocs, případně gSheets pro data jako seznam členů. K ani jedné z této variant, nepotřebuje uživatel téměř žádné nestandartní znalosti k tomu, aby informace zaznamenal. Pokud mu bude dán odkaz na dokument do kterého má zápis udělat, a pod jaký nadpis, mělo by to stačit každému. Jako kritérium pro vyhodnocení kandidátů z hlediska zápisu proto bude, zda vyžadují od uživatele znalost, jako například specifický jazyk k tomu, aby mohl zapisovat do uložiště. Pokud ano, nejsou pro návrh z hlediska zapisování do báze přijatelné.
##### čtení
Z hlediska čtení, respektive možností prohledávání uloženého obsahu. Podmínka z cíle říká, že čtení má být efektivní. Měřeno rychlostí na získání výsledků a správností výsledků. To znamená absenci jak chyb kdy je zobrazen výsledek neobsahujicí hledaný obsah (false positive), tak chyb kdy obsah hledaný uživatelem není nalezen, ikdyž ve skutečnosti je zaznamenán a měl by se zobrazit (false negative). Z kandidátu tedy budou vyřazeni ti, kteří toto nesplňují.
Pro zbývající pak bude vyhodnoceno stanovené kritérium příjemnosti využití. Definované jako co nejnižší bariera pro nové uživatele, kterou potřebují překonat aby mohli bázi prohledávat. Velikost bariéry pak bude měřena počtem znaků potřebných pro zadávání dotazů. A podle toho, zda k interakci s bází je v základu k dispozici webové grafické rozhraní. Počet nabízených funkcionalit bude vyhodnocen na základě dokumentace daného sw.
Zbývající kandidáti tedy budou porovnání podle počtu znaků vyžadovaných k napsání dotazu, přítomnosti webového grafického rozhraní ve výchozí instalaci báze. Vyhodnoceno bude nejdříve pořadí kandidátů podle každého z těchto dvou kritérií zvlášť. Následně takto získané ~~tři~~ hodnoty pro kaďého z kandidátů budou sečteny a kandidát, který bude mít nejnižší výsledné číslo, protože se například podle každého kritéria umístnil na prvním místě, bude vybrán pro použití v navrhované bázi.
#### Analýza vabraných zdrojů (sw)
~~Vybraní kandidáti budou následně stručně představeni a~~ 
Pro vybrané sw kandidáty bude určeno:
1. Jak vybrané softwary ukládají zaznamenané údaje?
2. Jak je možné programově přistupovat k zaznamenaným údajům ve vybraných softwarech?

- Je možné eliminovat či alespoň zcela minimalizovat potřebu lidských i finančních zdrojů na údržbu konzistence údajů ve vybraných softwarech zaznamenaných?
##### datové struktury (uložení)

##### integrovatelnost (přístup)

#### Vyhodnocení výsledků analýzy (sw)
##### ==prostředky vyžadované na údržbu==
Vycházeje z výsledků, získaných vyhodnocením předchozích dvou analytických otázek, bude určeno, zda je možné na základě vybraných sw kandidátů možné postavit bázi, která jak specifikuje cíl práce, nebude vyžadovat víc prostředků na provoz a údržbu než sama ušetří. To konkrétně bude provedeno pomocí nalezení způsobu jak eliminovat potřebu na ručně vykonávanou údržbu báze do stavu, kdy bude prohledávatelná a bude zobrazovat aktuální údaje. Při tomto hledání je vycházeno z předpokladu, že báze může ušetřit nějaký čas svým využitím, jen když nebude zároveň také vyžadovat čas na údržbu pro svojí správnou funkčnost. Rovněž by také neměla vyžadovat žádné finanční prostředky, jelikož vzhledem k neziskové povaze skauta není způsob, jak by se prostředky vydané na provoz takového systému mohly vrátit.
V případě nalezení takového způsobu, bude způsob popsán a jeho proveditelnost argumentována dokumentací daných nástrojů.

## Metodika návrhu %% fold %% 
Nyní, se získanýmy pojmy tvořícími cílovou doménu, i vybranými vhodnými nástroji, které realizaci jako takovou umožní, je konečně čas na návrh. 
### ==model pojmů==

#### ==obecný postup== 
Hlavním cílem této části návrhu je poskytnutí odpovědi na otázku "Jak spolu ve skutečnosti souvisí pojmy asociované se skautskými programy?".
*Otázkou, na níž by vytvořený model měl poskytnout odpověď je: "Co jsou to skautské programy?". Respektive: "Které pojmy jsou asociovány se skautskými programy a jaké jsou přitom role jednotlivých asociovaných pojmů?"*
Tato část návrhu bude uskutečněna pomocí ==UML, jakožto velmi dobře standartizovaného nástroje pro modelování struktur i skutečnosti obecně. Ve verzi 2.5.1 ze které aktuálně výcházím, má i celou druhou polovinu zaměřenou na stavy, chování, akce interakce, až případy užití. Ač se jedná o velmi užitečnou část, na její využití v této práci pravděpodobně nedojde z důvodu času a rozsahu práce.
Jediná odchylka od standardu UML bude provedena v případě generalizace, která místo běžné verze:
![[myDM/Zotero/LiteratureNotes/UnifiedModelingLanguage#^N57FEDGRaIAQSHBP8p145]]
bude pro generalizace využívat následující notaci.
[]
Je tak učiněno z toho důvodu, že v používaném modelovacím nástroji (draw.io) je jednoduší s modelem manipulovat (posouvat jednotlivé části) v případě využití alternativní notace pro modelování generalizací.==

==Konkrétně z UML bude při návrhu využit diagram tříd. Který bude sestaven s pomocí nalezených pojmů a mých doménových znalostí, jakožto člena oddílu posledních 15 let a jako vedoucího posledních 6 let. Při tvorbě diagramu bude postupováno podle následujícího postupu.==
#### ==konkrétní postup== 
##### 1. Základní definice skautských programů
==Nejdříve budou určeny vztahy mezi záznamy z jednotlivých existujících bází. Jelikož každá z nich se na problematiku skautských programů dívá z jiného pohledu, agregací těchto pohledů by měla vzniknout poměrně přesná definice skautských programů. 
Prvním krokem sestavení základní definice modelované domény, bude určení 1-2 pojmů z každé existující báze, které nejlépe vystihují, co je v dané bázi zaznamenáno. Vybrané pojmy a jejich vztahy budou vymodelovány pomocí jednoduchého, ale pravdivého modelu, který tak poskytne základní prvek tvořeného diagramu. S tím, že tento základní prvek, bude v následujících krocích tvorby diagramu obohacován a doplňován pojmy získanými literární analýzou.==

##### 2. ==Rozšíření definic tříd ze základní definice skautských programů
==
vybrat pojmy z chystamprogram asociovatelné i s událostmi .
vybrat pojmy z popisu obsahu sdíleného disku asociovatelné i s aktivitami 
vybrat pojmy z encyklopedie her asociovatelné s uálostmi i  s aktivitami

Je možné asociovat některé pojmy ze specializovaných tříd s jim generalzovanou třídou?


Pokud má pojem asociovaný se třídou A stejný či velmi podobý název jako jiný pojem asociovaný s odlišnou třídou B, ale liší se v přípustných hodnotách, je na tyto pojmy pohlíženo jako na rozdílné. To znamená, že pojmy odpovídající této podmínce, nebudou sloučeny prostřednictvím generalizované třídy (v tomto případě Program), nýbrž budou vymodelovány dvě oddělené třídy, jednu pro každou z tříd (v tomto případě Aktivita, Událost). Příkladem může být 'místo konání'. V bázi chystamprogram tento pojem může reprezentovat hodnoty npř. místnost, louka,... . Zato v případě asociace s událostí jsou tímto pojmem typicky označovány přibližné i konkrétní geografické lokace, kde se děti s vedoucími budou v průběhu události pohybovat, případně nocovat, pokud se jedná o vícedení událost. Místem konání pro události tak bývají například konkrétní skautské klubovny, souřadnice tábořiště etc.

Pokud ale stejný pojem i stejné reprezentované hodnoty, pak sloučit prostřednictvím generalizované třídy.

Obohacování modelu, je vždy prováděno vzhledem ke konkrétnímu pojmu ze základní definice.
	1. Nějaké gen/spec mezi vztahy vybranými k obohacení modelu?
	2. vlastnost(atribut:string||atribut:enumeration)
	3. asociace s třídou
		1. asociace sama se sebou
	4. specializovaná třída
	

aktivita
vybrat pojmy vyskytující se v chystamprogram a zároveň encyklopedii 
(chystamprogram - program) + (hry - program) 


hra
vybrat pojmy z encyklopedie, které se nevyskytují v chystamprogram 
(hra - program -aktivita)

událost
vybrat poojmy z popisu obsahu sdíleného disku.

Případně mohou být pro dosažení lepší srozumitelnosti modelu využity následující úpravy. Pokud by třída A měla stejný vztah k třídě B i C, bude vymodelována nová třída D, která bude generalizací tříd B a C. Bude tím pádem možné modelovat vztah pouze jednou. Podobná logika bude využita v případě že třída M bude mít vztah ke třídě N, ale ne vždy. Budou vytvořeny dvě podtřídy pro třídu N, první třída O, která bude mít povinný vztah se třídou M. A druhou třídu P, která tento vztah s M nemá.

Rozhodnutí, zda modelovat pojem P jako atribut třídy TI, nebo oddělenou třídu TP, která je s třídou TI asociována, bude učiněno v závislosti na tom, zda pojem P je asociován ještě s dalšími třídami kromě třídy TI. 
Rovněž bude využito oddělené třídy, pokud instance třídy TP vytvořené z pojmu P mohou mít vztah s více instancemi asociované třídy TI zároveň.
### db schema
- [x] [Ttyp::EXTRAHOVAT]|[] #p/bp/metodika/dbschema ✅ 2024-05-04

==Hlavním cílem této části bude poskytnutí odpověďi na otázku "Jak by měl obsah, uložený v navržené bázi, být strukturován, aby umožňoval požadované možnosti prohledávání?".
-
Získání schematu databáze z konceptuálního modelu by bylo možné alespoň dvěma hlavními způsoby. První z nich by byl využitím poměrně jednoduchého algoritmu, který z logického relačního modelu vytvoří schema pro databázi grafovou [ ]. Jelikož i získání relačního modelu z již vytvořeného konceptuálního je velmi přímočaré, mohla by toto být snadná cesta k cíli. A pravděpodobně i je, nicméně takto vytvořený graf nebere v úvahu doporučení identifikovaná v několika oficiálních zdrojích Neo4j jako nejlepší praktiky pro modelování grafových dat, tak aby umožňovaly optimální využití. To znamená, že pravděpodobně bude následně ještě vyžadovat určité své části refaktorovat, aby využil naplno možností, které uložení v grafové struktuře nabízí. V rámci jazyka pro interakci s Neo4j existují i funkce pro snadné refaktorování uložené struktury, takže i to by bylo použitelné řešení. Vhodnější však v případě, že už by nějaká relační báze byla k dispozici, než v tomto.
Postup této práce se mírně liší v tom ohledu, že nejprve v teoretické části představí ony nejlepší praktiky pro modelování grafů. Které jsou popsány v dokumentaci Neo4j [ ], knize Graph Databases od vydavatelství OReilly věnující se rovněž databázi Neo4j [ ] a navíc ještě na blogu jednoho z developerů Neo4j na serveru Medium [ ]. Bude se jednat o sadu doporučení pro jednotlivé prvky grafu {lable, relation, property, node} jak by měly být optimálně využívány. A tyto doporučení aplikuje na konceptuální model vytvořený v praktické části. Výsledné schema grafové databáze získané transformací konceptuálního modelu bude následně prezentováno v kapitole praktické části 'Návrh schema databáze'. Dohromady spolu s popisem, která doporučení byla aplikována a na které části původního modelu.==
## Ověření
- [x] [Ttyp::EXTRAHOVAT]|[] #p/bp/metodika/ověření ✅ 2024-05-04

Na závěr praktické části práce, bude provedena verifikace navržené infrastruktury, zda je v teoretické části popsaný způsob její realizace opravdu proveditelný. Navíc bude verifikována i funkcionalita navrženého schématu databáze, zda opravdu umožňuje takové prohledávání, jako by podle požadavků stanovených v této práci měl.

### Ověření úspěšnosti výběru pojmů


### Ověření technické realizovatelnosti návržené infrastruktury
==Verifikace realizovatelnosti navržené infrastruktury bude provedena pomocí experimentu. Prvním krokem v tomto experimentu pak bude definování klíčových prvků návrhu, a definování funkcionalit návrhu, které na těchto prvcích závisí. Druhým krokem potom bude implementace definovaných klíčových prvků a porovnání chování implementovaného systému s tím definovaným v prvním kroce experimentu. Pokud se tato chování nebudou lišit, bude to interpretováno jako důkaz, že návrh infrastruktury báze je proveditelný.==
### Ověření úspěšnosti tvorby konceptuálního modelu
#### "Dokončení" modelu
==Pro určenení dostatečné dokončenosti modelu pojmů na to, aby bylo možné přejít k návrhu schemata pro vlastní bázi, budou použity takzvané 'kompetenční otázky'. Jedná se o pojem využívaný například při tvorbě ontologií [ ], nebo i v případě modelování grafových dat například pro Neo4j [ ]. V obou případech pojem 'kompetenčních otázek' znamená otázky na které by vytvořená struktura "uměla odpovídat". Nejpochopitelnější je to na příkladu otázek pro bázi jako Neo4j, kdy je snadné si představit, že aby byla báze schopná vám vracet odpovědi na specifické dotazy, musí struktura uložených dat obsahovat všechny údaje potřebné k tomu, aby "uměla odpovědět". Proto se takto stanovené otázky následně užívají jako vodítko při modelování, jelikož pomáhají tvůrci udržet pozornost na zamýšleném účelu pro tvořenou bázi, model, či ontologii.==

==*Konkrétní kompetenční otázky budou založeny na schopnostech existujících bází odpovídat*. To znamená, že pokud umožňuje báze chystamprogram hledat aktivity podle toho, které oblasti Stezky odpovídají. Bude odvozená otázka: "Které aktivity jsou asociované s danou oblastí Stezky?". Pro model to tak znamená, že musí obsahovat asociaci mezi třídami oblast_Stezky a aktivita.==
S pomocí těchto otázek tedy bude dokoknčeno definování modelované domény. Myšleno pro tuto itaraci. Jelikož strukturování znalostí je nutně iterativní proces, který nemá žádné jedno správné řešení. Ale závisí vždy na konkrétní aplikaci a plánovaných rozšířeních. [ ]
A konkrétní aplikace v tomto případě je prostředek pro náš oddíl, který by mu umožnil efektivně a příjemně vyhledávat ve sdílených záznamech. *S podporou alespoň stejných možností parametrizace uložených programů, jako umožňují ostatní zmiňované implementace*. Pokud tedy takového stavu bude dosaženo, výsledek bude popsán v kapitole 'Návrh konceptuálního modelu' praktické části práce. A přijde na řadu samotná báze a její struktura.

### Ověření vyhledávací funkcionality navrženého db schematu %% fold %% 
==Pro dokázání korektního převedení z konceptuálního modelu do schema databáze bude opět využito experimentu. Rovněž bude využita implementovaná databáze vytvořená v rámci ověření realizovatelnosti infrastruktury. Do této databáze budou nahrána vzorová data, které budou získána z existujících zápisů jak v bázi chystamprogram, tak Velké encyklopedie her. Následně na základě kompetenčních otázek použitých při tvorbě konceptuálního modelu, budou sesteveny dotazy v jazyce používaným databází a definovány očekávané výsledky, které by dotazy měly zobrazit na základě nahraných vzorových dat. Na závér budou zadány připravené dotazy do rozhraní implementované databáze a vrácené výsledky budou porovnány s těmi, které by se podle definice měly zobrazit. Pokud se tyto výsledky nebudou lišit, bude to interpretováno jako důkaz, že navržená báze splňuje podmínky na možnosti prohledávání stanovené cílem této práce.==


# výstupy interpretace(modelpojmů) podle starý metodiky
postupné rozšiřování modelu pro základní pojmy a získání tak agregovaného pohledu na zkoumanou doménu.

Toho je docíleno zaprvé tak, že jsou nejdříve představeny výsledky z dílčího kroku 'zakreslení pojmů' ve formě modelu, jenž má pouze umístněné zakreslené pojmy v blízkosti základních pojmů, avšak neobsahuje zatím žádné asociace.  
S jedinou vyjímkou atributů základních tříd, jejichž datovým typem je buď boolean nebo intager, ty jsou totiž již při zakreslování umístněny "dovnitř" odpovídající základní třídy. Bylo tak učiněno z důvodu lepší přehlednosti modelu. Konkrétně byl postup vybrán jakožto nejsnažší možnost na "zbavení se" části pojmů, rychle, hned na začátku, pomocí snadno vyhodnotitelného kritéria a usnadnění tak celého dalšího modelování.

A zadruhé, jsou prezentovány výsledky z kroku 'modelování pojmů'. ==Není však představen celý model najednou, nýbrž jsou představený postupně dílčí pohledy, na část vytvořeného modelu odpovídající jendotlivým základním třídám, počínaje od té nejvíce generalizované.==  
Pro každý z těchto dílčích pohledů na model je následně poskytnut podrobný popis vyseče reality, který je jím zobrazen. Zároveň je také doručena argumentace pro jednotlivá rozhodnutí, učinněná v rámci procesu modelování pojmů, a tím tak odůvodněno, proč jsou konkrétní pojmy vymodelovány tak jak jsou vymodelovány a ne jinak.

# no. to je zrovna špatnej příklad
Hlavní existující strukturou, jež byla hledána, jsou hierarchie mezi existujícími získanými pojmy. Příkladem mohou být pojmy 'věk skupiny', 'věk nejmladšího', 'věk nejstaršího',

a thole mi tak pŕekáží 
shlukovat specializace podle stejné logiky pomocí nové generalizované třídy || gen class if > 2 tříd specializovaných podle stejné logiby (obsahují typicky v názvu stejné slovo)
# pokus o syst tvorbu modelu chápaní významu atributů
 Prvně jsou pojmy z výsledků analýzy obsahu bází převedeny do jednotného čísla, pokud jsou napsány jinak a z každého z nich je následně vytvořena jedna třída, se stejným názvem jako daný pojem, v modelovacím nástroji reprezentovaná obdélníkem.

*Předtím, než byla provedena "hlavní" modelovací část, bylo zapotřebí nejdříve získané pojmy do modelovacího (kreslícího) nástroje zakreslit.*
-  atributy typů bool,int vymodelovat do vlastnictví odpovídajících základních tříd
 Třídy, jenž reprezentují pouze binární hodnotu (ano, ne) nebo jedinou číselnou hodnotu, byly modelovány jako atributy, jim přiřazených, tříd základních.

pro komplexnější pojmy, jejichž 


- enumerations z existujících bází (také částečně kvůli "kompatibilitě" záznamů)



- zbylé pojmy (classes)
1. hierarchie mezi existujícími asociovanými pojmy

2. další povinné vztahy mezi asociovanými

3. Shlukovat specializace podle stejné logiky pomocí nové generalizované třídy || gen class if > 2 tříd specializovaných podle stejné logiby (obsahují typicky v názvu stejné slovo)

4. asociace se základními třídami,

5. doplněné alespoň jednoho atributu ke každé nespecializované třídě

# metodika-interpretace->modelpojmů %% fold %% 
Konkrétně z UML ==byl při návrhu využit diagram tříd. Který byl sestaven s pomocí nalezených pojmů a mých doménových znalostí, jakožto člena oddílu posledních 15 let a jako vedoucího posledních 6 let. ==

Při tvorbě diagramu bylo postupováno podle následujícího postupu.

"""
##### Základní definice
==Nejdříve byly určeny vztahy mezi obsahem z jednotlivých existujících bází. Jelikož každá z nich se na problematiku skautských programů dívá z jiného pohledu, agregací těchto pohledů by měla vzniknout lepší a přesnější základní definice skautských programů, než v případě využití pouze jedné báze. Pro její získání byly využity základní pojmy, charakterizující obsah jednotlivých bází, získané předchozím krokem.
-
Získané základí pojmy a jejich vztahy jsou vymodelovány pomocí jednoduchého, ale pravdivého diagramu tříd, který tak poskytne základní strukturu tvořeného diagramu. 
-
S tím, že tento základní prvek, bude v následujím postupu tvorby diagramu obohacován a doplňován pojmy získanými literární analýzou.==
##### Rozšíření definice
 Rozšíření definice

==Cílem je vhodné asociování získaných pojmů k základním třídám reprezentujícím doména skautských programů "7/10"

## ==zakreslení pojmů==

- roztřídit podle asociovatelnosti se základními třídami (+implicitně se zbavit duplikátů )  
    + ujednocení do Jednotného čísla
- A* atributy (boolean,int) k základním třídám
- B*sets z originálních bází,  
    pomocí takzvaných číselníků, neboli "enumerates"  
    (OFFaby zůstala Zachovala kompatibilitaOFF)  
    + * classes

## ==modelování pojmů==

1. hierarchie mezi existujícími asociovanými pojmy

2. další povinné vztahy mezi asociovanými

3. Shlukovat specializace podle stejné logiky pomocí nové generalizované třídy || gen class if > 2 tříd specializovaných podle stejné logiby (obsahují typicky v názvu stejné slovo)

4. asociace se základními třídami,

5. doplněné alespoň jednoho atributu ke každé třídě==

## 
pro každý základní p/t:
	z výsledků vybrat asociovatelné pojmy

[huh? jasně, že jo, co to je za otázku?] Je možné asociovat některé pojmy ze specializovaných tříd s jim generalzovanou třídou?

==deduplikace
Pokud má pojem asociovaný se třídou A stejný či velmi podobý název jako jiný pojem asociovaný s odlišnou třídou B, ale liší se v přípustných hodnotách, je na tyto pojmy pohlíženo jako na rozdílné. To znamená, že pojmy odpovídající této podmínce, nebudou sloučeny prostřednictvím generalizované třídy (v tomto případě Program), nýbrž budou vymodelovány dvě oddělené třídy, jedna pro každou z tříd (v tomto případě Aktivita, Událost). Příkladem může být 'místo konání'. V bázi chystamprogram tento pojem může reprezentovat hodnoty npř. místnost, louka,... . Zato v případě asociace s událostí jsou tímto pojmem typicky označovány přibližné i konkrétní geografické lokace, kde se děti s vedoucími budou v průběhu události pohybovat, případně nocovat, pokud se jedná o vícedení událost. Místem konání pro události tak bývají například konkrétní skautské klubovny, souřadnice tábořiště etc.
-
Pokud ale má pojem A minimálně rozdílný název od pojmu B a zároveň i reprezentuje stejné hodnoty, pak je pojem s daným názvem převeden do vlastnictví generalizované třídy.==

[nahh, tohle nechci] Obohacování modelu, je vždy prováděno vzhledem ke konkrétnímu pojmu ze základní definice.
	1. Nějaké gen/spec mezi vztahy vybranými k obohacení modelu?
	2. vlastnost(atribut:string||atribut:enumeration)
	3. asociace s třídou
		1. asociace sama se sebou
	4. specializovaná třída
	
==programy
	vybrat pojmy z chystamprogram asociovatelné i s událostmi .
	vybrat pojmy z popisu obsahu sdíleného disku asociovatelné i s aktivitami 
	vybrat pojmy z encyklopedie her asociovatelné s uálostmi i  s aktivitami
-
aktivita
vybrat pojmy vyskytující se v chystamprogram a zároveň encyklopedii 
(chystamprogram - program) + (hry - program) 
kdy modelovat pojem jako třídu a kdy jako atribut
-
hra
vybrat pojmy z encyklopedie, které se nevyskytují v chystamprogram 
(hra - program -aktivita)
-
událost
vybrat poojmy z popisu obsahu sdíleného disku.==
'''
Případně mohou být pro dosažení lepší srozumitelnosti modelu využity následující úpravy. Pokud by třída A měla stejný vztah k třídě B i C, bude vymodelována nová třída D, která bude generalizací tříd B a C. Bude tím pádem možné modelovat vztah pouze jednou. Podobná logika bude využita v případě že třída M bude mít vztah ke třídě N, ale ne vždy. Budou vytvořeny dvě podtřídy pro třídu N, první třída O, která bude mít povinný vztah se třídou M. A druhou třídu P, která tento vztah s M nemá.  [jako true, ale naštěstí tam takovýhle srandy nedělam]

Rozhodnutí, zda modelovat pojem P jako atribut třídy TI, nebo oddělenou třídu TP, která je s třídou TI asociována, bude učiněno v závislosti na tom, zda pojem P je asociován ještě s dalšími třídami kromě třídy TI. [nesmysl, i v případě atributu je možné aby ho využívalo více tříd]
Rovněž bude využito oddělené třídy, pokud instance třídy TP vytvořené z pojmu P mohou mít vztah s více instancemi asociované třídy TI zároveň. [taky nesmysl, to může v pohodě i atribut]

"""

# 
## Metodika zakončení
![[BP/assets/diskuze-metodika-UMLactivity.jpg]]

![[BP/assets/zaver-metodika-UMLactivity.jpg]]




# 
  
  // A minimálně stejného množství parametrů použitelných pro vyhledávání v záznamech jako umožňuje existující báze chystamprogram.
# 
##### 3. Dopnění kontextu

###### doplnění generalizací/specializací
Případně mohou být pro dosažení lepší srozumitelnosti modelu využity následující úpravy. Pokud by třída A měla stejný vztah k třídě B i C, bude vymodelována nová třída D, která bude generalizací tříd B a C. Bude tím pádem možné modelovat vztah pouze jednou. Podobná logika bude využita v případě že třída M bude mít vztah ke třídě N, ale ne vždy. Budou vytvořeny dvě podtřídy pro třídu N, první třída O, která bude mít povinný vztah se třídou M. A druhou třídu P, která tento vztah s M nemá.

###### doplnění volitelných vztahů
Rozhodnutí, zda modelovat pojem P jako atribut třídy TI, nebo oddělenou třídu TP, která je s třídou TI asociována, bude učiněno v závislosti na tom, zda pojem P je asociován ještě s dalšími třídami kromě třídy TI. 
Rovněž bude využito oddělené třídy, pokud instance třídy TP vytvořené z pojmu P mohou mít vztah s více instancemi asociované třídy TI zároveň.
# 
### Doplnění kontextu
#### 6.
Provedené úpravy model

reasoning
#### 7.
Provedené úpravy model

reasoning

# 

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