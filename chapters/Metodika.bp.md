# Úvod -motivace(problém)
![[BP/drafts/Zaměření.bp#Problém]]
# Úvod -cíl
![[BP/drafts/Zaměření.bp#Cíl]]
# Úvod -dílčí cíle
![[BP/drafts/Zaměření.bp#Dílčí cíle metody]]
# Úvod -výstupy
- seznam pojmů asociovaných se skautskými programy v existujících bázích
- konceptuální model domény skautských programů
- infrastruktura pro bázi
- schema databáze

Úvod -přínosy

# Úvod -struktura
S tím, že nejdříve v kapitole Metodika bude představen postup pro dosažení návrhu. Následně v teoretické části práce budou prezentovány výsledky výběru pojmů z modelované domény a výsledky výběru sw řešení pro ukládání a přístup k vybraným údajům. V části praktické pak bude představen navržený model, sestavený z pojmů získaných v rámci prvního dílčího cíle. Spolu se schématem pro databázi vybranou v rámci drůhého dílčího cíle. Nakonec v kapitole Diskuze bude provedeno zhodnocení dosažení stanovených cílů a posouzeny možnosti pro další práci.
![[../assets/metodika-UMLactivity.svg]]

- první dílčí cíl je analýza sw, ne analýza domény. Diagram tříd je vytvářený až v praktické části protože tento proces není tak triviální, jako vybrat sw podle jasných požadavků a podmínek. Zároveň diagram tříd představuje stále část analýzy domény skautských programů, respektive její závěrečnou fázi, kterážto má za úkol vyhodnotit a zpracovat výsledky získané analýzou.



# Metodika v3
![[../assets/analyzaswkandidatu-metodika-UMLactivity.jpg]]

![[../assets/analyzadomenyskautskychprogramu-metodika-UMLactivity.jpg]]

![[../assets/tvorbadbschematu-metodika-UMLactivity.jpg]]

![[../assets/overenivysledku-metodika-UMLactivity.jpg]]

![[../assets/diskuze-metodika-UMLactivity.jpg]]

![[../assets/zaver-metodika-UMLactivity.jpg]]



# metodika v2 %% fold %% 
## Metodika analýzy
### pojmy asociované se skautskými programy

#### Účel analýzy
Cílem této části práce je vybrání pojmů, kteréžto budou představovat odpověď na otázku "Co zaznamenávát v navrhované bázi?". Abych zjistil jaké informace jsou relevantí pro zaznamenávání v bázi skautských programů, provedu analýzu literatury z této oblasti podle doporučení specifikovaných Bernedtsonem a spol. v jejich knize.
[[myDM/Zotero/LiteratureNotes/berndtssonThesisProjectsGuide2008#^4VZXLNGCaNT5KVCQVp67]]
![[myDM/Zotero/LiteratureNotes/berndtssonThesisProjectsGuide2008#^TNTKU53KaNT5KVCQVp68]]
Podle autorů je hlavním cílem této metody, mimo získání konkrétních hledaných údaju, aby čtenář práce pochopil strategii pro hledání a výběr hledaných údajů. Samozřejmě by měl také znát a chápat konkrétní důvod proč je analýza prováděna. 
Duvod k analýze byl již stanoven, proto v následující podkapitole budou nejprve představeny dostupné zdroje, spolu s jejich přednostmi i nevýhodami, aby měl čtenář šanci porozumět proč byly, či nybyly vybrány k analýze. A aby čtenář nepochyboval o tom, zda je, vzhledem k cíli práce, analyzováno dostatečné množství zdrojů. V následující podkapitole pak bude popsán konkrétní způsob výběru pojmů z analyzovaných zdrojů, aby měl čtenář šanci pochopit jak byly výsledky získány, proč právě takovým způsobem a co získané údaje reprezentují.
#### Analyzované zdroje(báze)
Dostupnou literaturu představují již existující báze, které poslouží zároveň jako inspirace svým obsahem a zároveň jako prostředek pro porovnání možností prohledávání s navrhovanou bází.
Co se kvality a vhodnosti pro potřeby práce týče, představují existující báze zcela optimální zdroje k analýze. Navíc vzhledem k tomu, že i rozsah těchto zdrojů je větší, než je vůbec možné v rámci limitovaného rozsahu této práce využít, není prováděno hledání dalších analyzovatelných zdrojů.

První z existujících bází je webová stránka 'chystamprogram.skaut.cz', jenž byla vytvořena organizací Junák - český skaut, která zároveň za celý obsah zcela zodpovídá. [[../../myDM/Zotero/LiteratureNotes/ChystamProgramOProjektu#^NMC5UM33aSNYTTS96]] 
Její předností je zaměření na výchovnou a rozvojovou hodnotu programů. To je především zprostředkováno díky možnosti zapisovat k jednotlivým programům jejich výchovný cíl. Ale také možností zapisovat, na který bod ve Stezce je program napojen. Což je dobré a užitečné proto, že Stezka nepředstavuje jen rámec pro děti, podle kterého by se mohly samy všestranně rozvíjet. Rovně ale jako pomůcka pro vedoucí, když připravují vhodný program pro nadcházející schůzku například. [[myDM/Zotero/LiteratureNotes/StezkyCestickyVlcat#^N5AJVIHJa43Y7SWYU]] 
Drobná nevýhoda však vyplývá z toho, že se jedná o veřejnou bázi za kterou zodpovídá samotná organizace Junák. A to sice, že pro zapsání nového programu, je potřeba být přihlášen skautským účtem ze skautIS a výsledný zápis musí být nejdříve ověřen jejich metodickým týmem. Což sice bude mít pravděpodobně pozitivní vliv na úroveň kvality zaznamenaného obsahu. Nicméně pro sdílení například programu, který je teprve připravován, to tak není vhodné řešení. Jako větší nedostatek však vnímám spíše omezenou možnost poskytování zpětné vazby, a komentářu k zapsaným programům. Jediná možnost hodnocení, je totiž zaslání svého hodnocení pouze soukromě autorovi daného programu. Což opět pro interní využití, které by mělo umožňovat sdílení obsahu a na něm následnou spolupráci, není vyloženě příhodné.

Druhou bázi k analýze pak představuje 'Velká encyklopedie her'. Ta je tvořena čtyřmi samostanými tituly vydanými mezi lety 1987-1988, napsanými panem Milošem Zapletalem. [ ] Jak už název napovídá, jeji zaměření je čistě na hry, které jsou nepochybně také součástí skautských programů, těm se nicméně věnuje velmi podrobně. Slovo "Velká" v názvu totiž nijak zvlášť nepřehání. Každá z knih má v průměru přibližně 600 stran, sice menšího formátu, ale i přesto se často vejdou i dvě hry na stránku.
Právě tento objem, pědstavuje hlavní pědnost tohoto zdroje. Jelikož vzhledem k době jeho vydání, existuje šance, že některé zapsané hry, nebudou již dnes pro děti zábavné. Avšak vzhledem ke zmíněnému objemu, by se musela od té doby změnit kompletně celé podstata dětských her, aby tento zdroj již nebyl relevantní, což tato práce nepředpokládá.
S rokem vydání encyklopedie souvisí však i další nevýhody, které přehlédnout nelze. Klíčovým nedostatekm jou značně limitované možnosti efektivního prohledávání, které jsou implicitním důsledkem tištěné formy báze. Hry jsou sice jednotlivými knihami rozděleny podle prostědí do kterého jsou vhodné a dále pak pomocí kapitol. Navíc každá hra má vedle názvu uvedeno specifické značení, popsané na začátků každé z knih, které poskytuje informace například o tom, pro jaký počet, nebo věk hráču je hra vhodná. Nicméně to pořád znamená, že je třeba záznamy procházet manuálně a vizuálně kontrolovat, zda chci o dané hře číst více. Nemluvě o tom, že doplňování zpětné vazby či komentářů rovněž není možné.

Za existující bázi by se daly považovat i zápisy ke konkrétním programům na sdíleném disku našeho oddílu. Systematická analýza tohoto zdroje by však byla vzhledem k nesystematicky strukturovaným zápisům poměrně komplikovaná. Avšak pohled na zkoumanou problematiku touto bází je cenný, protože reprezentuje údaje, které jsou pro skautské programy považovány za důležité cílovími uževitali navrhované báze.
#### Analýza vybraných zdrojů (báze)
*analýza systematická X extrahování z rešerš*
Cílem analýzy těchto dvou zdrojů pak bude pro každý z nich zvlášť, zodpovědét následující dvě otázky.
- Jaké pojmy jsou využity bází k charakterizování zapsaných aktivit?
- *Podle jakých pojmů umožňuje báze prohledávat?* (-> Kompetenční otázky)
Vzhledem k rozdílným strukturám analyzovaných bází, budou odpovědi na otázky v každěm případě získány lehce odlišným způsobem.

Nejsnažší zodpovězení umožňuje báze chystamprogam, jelikož poskytuje šablonu pro nové záznamy s pojmenovanými a popsanými políčky(prvky) k vyplnění. 
Odpověd na první otázku je proto získána vypsáním názvů,jejich popisů, případně povolených hodnot pro všechny možné prvky ze šablony. 
K zodpovězení druhé jsou pak prohledýny poskytnuté filtry ve vrchní části stránky 'Hledat Aktivity' v této bázi a vypsány pojmy použité jako názvy parametrů umožňujících filtrování, stejně tak jejich přípustné hodnoty.

V případě tištěné encyklopedie je trochu problém, protože zápisy v ní nejsou na první pohled nijak systematicky strukturovány, kromě symbolického značení vedle názvů a svého zařazení do kapitol. Bylo by proto potřeba vybrat vzorek ze záznamů a na základě něj se pokusit určit jaká části se napříč záznamy vyskytují. Naštěstí jedna z encyklopedií zahrnuje ve své Úvodní kapitole část pojmenovanou "Jak zapisovat tradiční hry". Autor se v ní sice věnuje takzvaně tradičním dětským hrám. Tím má na mysli hry, které si děti hrají, ale jejich pravidla existují pouze jako sdílené vědomosti mezi hráči, nejsou však nikde popsána, tudíž je šance, že postupem času tyto hru upadnou v zapomění. Ač se autorova motivace liší od motivace této práce. Výčet parametrů relevantních pro hry, které v této části nabízí. Představuje podobně hodnotný zdroj, jako šablona pro zapisování v předchozí bázi. Pro získání odpovědi na první analytickou otázku proto budou vypsány pojmy právě z tohoto výčtu, nikoliv ze skutečně zapsaných her. 
Co se vyhledávání týče, to je zprostředkováno samotnými knihami, jejich kapitolami a symbolickým značením, u jednotlivých záznamů, popsaným za začátku knih. Proto právě z těchto částí by bylo vhodné získat odpovědi na druhou z analytických otázek. Kapitoly avšak, vzhledem ke značému rozsahu encyklopedie, obsahují příliš mnoho pojmů na to, aby je bylo možné, v rámci limitovaného rozsahu této práce, adekvátně systematicky vyhodnotit a nezanedbat v důsledku toho další klíčové části práce. Proto v rámci analýzy encyklopedie her, k zodpovězení druhé analitické otázky, bude použito pouze symbolické značení u jednotlivých her.

Aby bylo možné ve vytvořeném konceptuálním modelu zohlednit i pohled na problematiku očima cílových uživatelů navrhované báze, bude na závěr prezentovaných výsledků ze systematické analýzy prvních dvou bází v teoretické části, doplněna stručná rešerše obsahu uloženého na sdíleném disku. A na základě této rešerše budou identifikovany klíčové pojmy, které by měly být zakomponovány do modelu pojmů.

#### Vyhodnocení výsledků analýzy (báze)
základní pojmy/třídy
pro každý základní p/t:
	z výsledků vybrat asociovatelné pojmy

### infrastruktura vyhovující požadavkům práce
#### Účel analýzy

Kromě údajů, které by se měly ukládat, je také zásadní otázkou, jak a kde budou záznamy skutečně uloženy. Toto rozhodnutí ovlivňuje mimo konceptuální model všechnu další práci. V této části bude určeno právě místo pro uložení záznamů, které by splňovalo podmínky definované cílem této práce a tím tak představovalo odpověď na otázku "Kam uložit záznamy v navrhované bázi?". 
Kandidáty na uložiště jsou gDocs jakožto baseline, gSheets jakožto kompromis mezi databází a prostředím dokumentů. Třetím kandidátem je relační databáze MySQL. A nakonec databáze Neo4j jakožto reprezentace NoSQL. Všechny budou vyhodnoceny ze dvou hledisek (zápis, čtení). To znamená, že z jejich vyhodnocení získám dvě sady výsledků. 
#### Výběr zdrojů k analýze(sw)
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
##### prostředky vyžadované na údržbu
Vycházeje z výsledků, získaných vyhodnocením předchozích dvou analytických otázek, bude určeno, zda je možné na základě vybraných sw kandidátů možné postavit bázi, která jak specifikuje cíl práce, nebude vyžadovat víc prostředků na provoz a údržbu než sama ušetří. To konkrétně bude provedeno pomocí nalezení způsobu jak eliminovat potřebu na ručně vykonávanou údržbu báze do stavu, kdy bude prohledávatelná a bude zobrazovat aktuální údaje. Při tomto hledání je vycházeno z předpokladu, že báze může ušetřit nějaký čas svým využitím, jen když nebude zároveň také vyžadovat čas na údržbu pro svojí správnou funkčnost. Rovněž by také neměla vyžadovat žádné finanční prostředky, jelikož vzhledem k neziskové povaze skauta není způsob, jak by se prostředky vydané na provoz takového systému mohly vrátit.
V případě nalezení takového způsobu, bude způsob popsán a jeho proveditelnost argumentována dokumentací daných nástrojů.

## Metodika návrhu
Nyní, se získanýmy pojmy tvořícími cílovou doménu, i vybranými vhodnými nástroji, které realizaci jako takovou umožní, je konečně čas na návrh. 
### model pojmů

#### obecný postup 
Hlavním cílem této části návrhu je poskytnutí odpovědi na otázku "Jak spolu ve skutečnosti souvisí pojmy asociované se skautskými programy?".
*Otázkou, na níž by vytvořený model měl poskytnout odpověď je: "Co jsou to skautské programy?". Respektive: "Které pojmy jsou asociovány se skautskými programy a jaké jsou přitom role jednotlivých asociovaných pojmů?"*
Tato část návrhu bude uskutečněna pomocí UML, jakožto velmi dobře standartizovaného nástroje pro modelování struktur i skutečnosti obecně. Ve verzi 2.5.1 ze které aktuálně výcházím, má i celou druhou polovinu zaměřenou na stavy, chování, akce interakce, až případy užití. Ač se jedná o velmi užitečnou část, na její využití v této práci pravděpodobně nedojde z důvodu času a rozsahu práce.
Jediná odchylka od standardu UML bude provedena v případě generalizace, která místo běžné verze:
![[myDM/Zotero/LiteratureNotes/UnifiedModelingLanguage#^N57FEDGRaIAQSHBP8p145]]
bude pro generalizace využívat následující notaci.
[]
Je tak učiněno z toho důvodu, že v používaném modelovacím nástroji (draw.io) je jednoduší s modelem manipulovat (posouvat jednotlivé části) v případě využití alternativní notace pro modelování generalizací.

Konkrétně z UML bude při návrhu využit diagram tříd. Který bude sestaven s pomocí nalezených pojmů a mých doménových znalostí, jakožto člena oddílu posledních 15 let a jako vedoucího posledních 6 let. Při tvorbě diagramu bude postupováno podle následujícího postupu.
#### konkrétní postup 
##### 1. Základní definice skautských programů
Nejdříve budou určeny vztahy mezi záznamy z jednotlivých existujících bází. Jelikož každá z nich se na problematiku skautských programů dívá z jiného pohledu, agregací těchto pohledů by měla vzniknout poměrně přesná definice skautských programů. 
Prvním krokem sestavení základní definice modelované domény, bude určení 1-2 pojmů z každé existující báze, které nejlépe vystihují, co je v dané bázi zaznamenáno. Vybrané pojmy a jejich vztahy budou vymodelovány pomocí jednoduchého, ale pravdivého modelu, který tak poskytne základní prvek tvořeného diagramu. S tím, že tento základní prvek, bude v následujících krocích tvorby diagramu obohacován a doplňován pojmy získanými literární analýzou.

##### 2. Rozšíření definic tříd ze základní definice skautských programů

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

Hlavním cílem této části bude poskytnutí odpověďi na otázku "Jak by měl obsah, uložený v navržené bázi, být strukturován, aby umožňoval požadované možnosti prohledávání?".

Získání schematu databáze z konceptuálního modelu by bylo možné alespoň dvěma hlavními způsoby. První z nich by byl využitím poměrně jednoduchého algoritmu, který z logického relačního modelu vytvoří schema pro databázi grafovou [ ]. Jelikož i získání relačního modelu z již vytvořeného konceptuálního je velmi přímočaré, mohla by toto být snadná cesta k cíli. A pravděpodobně i je, nicméně takto vytvořený graf nebere v úvahu doporučení identifikovaná v několika oficiálních zdrojích Neo4j jako nejlepší praktiky pro modelování grafových dat, tak aby umožňovaly optimální využití. To znamená, že pravděpodobně bude následně ještě vyžadovat určité své části refaktorovat, aby využil naplno možností, které uložení v grafové struktuře nabízí. V rámci jazyka pro interakci s Neo4j existují i funkce pro snadné refaktorování uložené struktury, takže i to by bylo použitelné řešení. Vhodnější však v případě, že už by nějaká relační báze byla k dispozici, než v tomto.
Postup této práce se mírně liší v tom ohledu, že nejprve v teoretické části představí ony nejlepší praktiky pro modelování grafů. Které jsou popsány v dokumentaci Neo4j [ ], knize Graph Databases od vydavatelství OReilly věnující se rovněž databázi Neo4j [ ] a navíc ještě na blogu jednoho z developerů Neo4j na serveru Medium [ ]. Bude se jednat o sadu doporučení pro jednotlivé prvky grafu {lable, relation, property, node} jak by měly být optimálně využívány. A tyto doporučení aplikuje na konceptuální model vytvořený v praktické části. Výsledné schema grafové databáze získané transformací konceptuálního modelu bude následně prezentováno v kapitole praktické části 'Návrh schema databáze'. Dohromady spolu s popisem, která doporučení byla aplikována a na které části původního modelu.
## Ověření


Na závěr praktické části práce, bude provedena verifikace navržené infrastruktury, zda je v teoretické části popsaný způsob její realizace opravdu proveditelný. Navíc bude verifikována i funkcionalita navrženého schématu databáze, zda opravdu umožňuje takové prohledávání, jako by podle požadavků stanovených v této práci měl.

### Ověření úspěšnosti výběru pojmů


### Ověření technické realizovatelnosti návržené infrastruktury
Verifikace realizovatelnosti navržené infrastruktury bude provedena pomocí experimentu. Prvním krokem v tomto experimentu pak bude definování klíčových prvků návrhu, a definování funkcionalit návrhu, které na těchto prvcích závisí. Druhým krokem potom bude implementace definovaných klíčových prvků a porovnání chování implementovaného systému s tím definovaným v prvním kroce experimentu. Pokud se tato chování nebudou lišit, bude to interpretováno jako důkaz, že návrh infrastruktury báze je proveditelný.
### Ověření úspěšnosti tvorby konceptuálního modelu
#### "Dokončení" modelu
Pro určenení dostatečné dokončenosti modelu pojmů na to, aby bylo možné přejít k návrhu schemata pro vlastní bázi, budou použity takzvané 'kompetenční otázky'. Jedná se o pojem využívaný například při tvorbě ontologií [ ], nebo i v případě modelování grafových dat například pro Neo4j [ ]. V obou případech pojem 'kompetenčních otázek' znamená otázky na které by vytvořená struktura "uměla odpovídat". Nejpochopitelnější je to na příkladu otázek pro bázi jako Neo4j, kdy je snadné si představit, že aby byla báze schopná vám vracet odpovědi na specifické dotazy, musí struktura uložených dat obsahovat všechny údaje potřebné k tomu, aby "uměla odpovědět". Proto se takto stanovené otázky následně užívají jako vodítko při modelování, jelikož pomáhají tvůrci udržet pozornost na zamýšleném účelu pro tvořenou bázi, model, či ontologii.

*Konkrétní kompetenční otázky budou založeny na schopnostech existujících bází odpovídat*. To znamená, že pokud umožňuje báze chystamprogram hledat aktivity podle toho, které oblasti Stezky odpovídají. Bude odvozená otázka: "Které aktivity jsou asociované s danou oblastí Stezky?". Pro model to tak znamená, že musí obsahovat asociaci mezi třídami oblast_Stezky a aktivita.
S pomocí těchto otázek tedy bude dokoknčeno definování modelované domény. Myšleno pro tuto itaraci. Jelikož strukturování znalostí je nutně iterativní proces, který nemá žádné jedno správné řešení. Ale závisí vždy na konkrétní aplikaci a plánovaných rozšířeních. [ ]
A konkrétní aplikace v tomto případě je prostředek pro náš oddíl, který by mu umožnil efektivně a příjemně vyhledávat ve sdílených záznamech. *S podporou alespoň stejných možností parametrizace uložených programů, jako umožňují ostatní zmiňované implementace*. Pokud tedy takového stavu bude dosaženo, výsledek bude popsán v kapitole 'Návrh konceptuálního modelu' praktické části práce. A přijde na řadu samotná báze a její struktura.

### Ověření vyhledávací funkcionality navrženého db schematu %% fold %% 
Pro dokázání korektního převedení z konceptuálního modelu do schema databáze bude opět využito experimentu. Rovněž bude využita implementovaná databáze vytvořená v rámci ověření realizovatelnosti infrastruktury. Do této databáze budou nahrána vzorová data, které budou získána z existujících zápisů jak v bázi chystamprogram, tak Velké encyklopedie her. Následně na základě kompetenčních otázek použitých při tvorbě konceptuálního modelu, budou sesteveny dotazy v jazyce používaným databází a definovány očekávané výsledky, které by dotazy měly zobrazit na základě nahraných vzorových dat. Na závér budou zadány připravené dotazy do rozhraní implementované databáze a vrácené výsledky budou porovnány s těmi, které by se podle definice měly zobrazit. Pokud se tyto výsledky nebudou lišit, bude to interpretováno jako důkaz, že navržená báze splňuje podmínky na možnosti prohledávání stanovené cílem této práce.





