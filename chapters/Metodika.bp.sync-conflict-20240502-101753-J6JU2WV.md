---
up:
  - "[[../README|README]]"
---
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
Členění práce je provedeno podle doporučené struktury pro výzkumné práce IMRaD [ ]

První následující kapitolou je Metodika, ta s využitím výše uvedeného schématu definuje metody využité pro dosažení stanovených dílčích cílů. 
Výsledky definované metodiky, jsou prezentovány v částech Teorie a Vypracování.

Část Teorie zahrnuje výsledky i interpretaci výsledků 'analýzy softwarových kandidátů', která je použita jako metoda pro 1. dílčí cíl. Z 'analýzy existujících bází', metody zvolené pro dosažení 2. dílčího cíle, jsou však v teoretické části pouze její výsledky s nejstručnějším popisem.
Interpretace výsledků získaných 'analýzou existujících bází' je totiž uskutečněno sestavením diagramu tříd vycházejícího ze standardu UML. A jelikož proces konceptuálního modelování, narozdíl od přímočarého porovnávání softwaru, nepředstavuje triviální záležitost a zejména pak proto, že je vytvořený model přímým vstupem pro 'návrh schématu báze'(3.dílčí cíl), jsou výsledky z tvorby modelu(interpretace výsledků získaných analýzou existujících bází) podrobně popsány až v úvodu praktické části 'Vypracování'. Dále se v praktické části nachází popis navrženého schématu pro databázi, které bylo odvozeno z konceptuální modelu pomocí nejlepších praktik pro modelování dat ve vybrané databázi, identifikovaných autory databáze.

Na prezentované výsledky navazuje kapitola Diskuze, kterážto zahrnuje kromě 'ověření úspěšnosti dosažení cílů'(4.dílčí cíl) také vysvětlení získaných výsledků. Rovněž se tato kapitola vyjadřuje k limitacím přijatým pro dokončení práce a z nich vyplývající potenciální budoucí práci na zdokonalování nyní dosaženého návrhu.
Poslední kapitolou je pak Závěr, který shrnuje a hodnotí dosažení hlavního cíle práce (v tomto případě: 'návrh báze znalostí skautských programů').

Dalo by se tak také říci, že rozdělení textu dodržuje stejné dva principy aplikované pro lepší čitelnost a pochopitelnost kódu. 
Jedná se zaprvé 'Locality of behavior', která přeneseně (v původním znění je například použito výrazu zdrojový kód místo text) říká, že 'lokalita' je charakteristika textu, která umožňuje jeho čtenáři pochopení konkrétního obsaženého významu pouze z malé části celého textu [ ]. V praxi to tak má předejít situacím, kdy aby čtenář kódu pochopil co daný kód dělá, je nucen přecházet mezi několika soubory, což snadné a rychlé pochopení téměř určitě neusnadňuje. Ze stejného důvodu IMRaD definuje několik konkrétních částí, které optimalizují rozdělení textu o provedeném výzkumu z hlediska možných "typů chování" při kterých bude čtenář chtít využít daný popsaný výzkum. Jako typy chování je myšleno například vyhledávání zdrojů, pro toto chování jsou strukturou IMRaD následně definovány části titulek, abstrakt i úvod, pro podporu různých hledání.  
Co se druhého principu týče, je jím tkzvaný princip 'Separation of concerns'[ ]. Ten je realizován v jednotlivých sekcích pomocí podsekcí a dalšího dělení. Například sekce Úvod by měla být rozdělena na části adresující motivaci pro psaní práce, konkrétní řešený problém, hlavní cíl, dílčí cíle atd.. Rozdělení tak odpovídá jednotlivým 'starostem', které by čtenář v rámci čtení dané sekce mohl mít, nebo spíše starostí konkrétní části textu o předání specifické informace čtenáři.
Pokud je mnou provedené přirovnání chybné, uvítám připomínky.
![[myDM/Zotero/LiteratureNotes/wuImprovingWritingResearch2011#^ITPMW4Q5aMPNI3JCVp2]]

### schema full
Následující schéma, založené na notaci 'activity' z UML, reprezentuje strukturu této práce. Jsou v něm zobrazeny datové objekty(obdélníky) a aktivity(čtyřúhelníky se zaoblenými rohy). ...
- [ ] Doplnit podrobnější vysvětlení čtení použité notace [chap::úvod.struktura.schema]

![[../assets/metodika-UMLactivity.svg]]
Schéma struktury dosažení stanoveného cíle nezobrazuje část metodiky, jelikož celé schéma je reprezentací metodiky.



# Metodika v3
V této kapitole jsou definovány metody využité prací k dosažení dílčích cílů. Pro každý z cílů je nejprve definován a vysvětlen jeho účel, popsán a zdůvodněn konkrétní postup, případně i obecný postup, pokud je takový aplikován, a na závěr jsou identifikovány části práce, ve kterých jsou výstupy konkrétních metod prezentovány. 
## Metodika analýzy sw kandidátů
#### Účel postupu
Jelikož tato práce neklade na navrhovaný systém zrovna nízké nároky (viz. Cíl), nestačí pouze určit, který obsah zaznamenávat a opomenout přitom řádný výběr softwarového nástroje nebo nástrojů pro uložení zaznamenávaného obsahu. Zároveň nelze tento krok ani vynechat, poněvaďž bez volby alespoň konkrétního typu SW pro uložení dat(npř. RDB, GDB, ...), není možné navrhnout ani konkrétní strukturu nové báze. Co víc, toto rozhodnutí ovlivňuje mimo konceptuální model, jakožto prostředek nezávislý na konkrétní implementaci, všechnu budoucí práci na vývoji, údržbu nasazeného systému i šanci na to, aby byla navržená báze skutečně cílovými uživatly přijata a využívána. Proto byl zvolen **dílčí cíl:** "Vybrat sw řešení umožňující dosažení cíle práce.". A účelem tohoto postupu proto je určení místa (SW nástroje) pro uložení záznamů navrhovanou bází, které by splňovalo požadavky definované cílem práce (viz. Cíl) a tím tak bylo odpovědí na otázku "Kam uložit záznamy v navrhované bázi?".

Záměrem však není ani tak podrobná či kompletní analýza veškerých dostupných nástrojů, spíše jako porovnání několika softwarových zástupců (kandidátů) s odlišnými typy datových struktur, které se obvykle pro stavbu bází využívají, a zjištění, kteří kandidáti splňují požadavky stanovené v cíli (viz. Cíl). 

Jako typy datových struktur k posouzení byly zvoleny dokumenty jakožto výchozí možnost, spreadsheets jakožto kompromis mezi databází a prostředím dokumentů, relační databáze jakožto prakticky standart při tvorbě znalostních bází a grafová databáze jakožto modernější varianta klasické relační DB. Konkrétními kandidáty posuzovanými na funkci uložiště záznamů navrhované báze, reprezentující jednotlivé typy zvolených datových struktur, jsou gDocs za dokumenty, gSheets za spreadsheets strukturu, MySQL za RDB a nakonec databáze Neo4j jakožto reprezentace GDB a NoSQL.
První dva SW kandidáti byly zahrnuti do výběru také proto, že se jedná o nástroje aktuálně v našem oddíle využívané, což znamená, že cíloví uživatelé navrhovaného systému již mají určité standardy, na než jsou zvyklí, že systém nabízí. A jak je prací stanoveno, tyto kvality by neměly být návrhem zredukovány, ba naopak by mělo být provedeno jejich rozšíření. Z toho důvodu jsou zahrnuti druzí dva SW kandidáti, jelikož disponují funkcemi, které v aktuálním řešení chybí.
#### Obecný postup
Pro dosažení prvního dílčího cíle byla zvolena metoda 'analýza literatury' dodržující postup popsaný Bernedtssonem a spol. (berndtssonThesisProjectsGuide2008). Autoři knihy uvádějí, že účelem této metody, mimo získání konkrétních hledaných údajů, je přesvědčení čtenáře práce o tom, že bylo analyzováno dostatečné množství, dostatečně kvalitních a relevantních zdrojů. 
Aby čtenář mohl udělat názor o tom, zda byly zdroje dostatečně relevantní, potřebuje znát konkrétní zamýšlený účel se kterým je analýza prováděna. Jasně definovaný účel je pak podle autorů klíčovým prvkem rovněž i pro autora analýzy, jelikož pokud si autor nebude konkrétního účelu vědom nebo ho bude přehlížet, jeho šance na přesvědčení čtenářů o validitě a přínosnosti prováděné analýza značně klesá. Zároveň specifický účel k provedení odlišuje 'analýzu literatury' od 'rešerše literatury', kterážto má primární účel seznámit autora i čtenáře s obsahem literatury z dané oblasti. [ ]
Autoři knihy dále identifikují následující kroky, které by jak v zájmu autora tak i čtenáře měly mít jasně definovanou strategii provedení. [[myDM/Zotero/LiteratureNotes/berndtssonThesisProjectsGuide2008#^ZIT8YCXSaNT5KVCQVp67]]
- **Výběr literatury:** Zahrnuje vyhledávání relevantních zdrojů a literatury související s tématem projektu.
  Jasně definovaná strategie pomůže, aby čtenář nepochyboval že byly provedeno adekvátní hledání zdrojů.
- **Hodnocení zdrojů:** Kritické posouzení zdrojů na základě jejich relevance a spolehlivosti.
  ..., aby čtenář nepochyboval o dostatečném objemu a dostatečné kvalitě zpracovaných zdrojů. 
  ..., aby čtenář porozumněl proč byly některé zdroje vybrané a jiné vynechané.
- **Analýza obsahu:** Podrobné zkoumání a získávání informací z vybraných zdrojů.
  ..., aby měl čtenář šanci pochopit jak byly výsledky získány.
- **Interpretace výsledků:** Integrace zjištění do koherentního celku a formulace závěrů.
  ..., aby čtenář rozumněl co získané údaje reprezentují.
### Konkrétní postup
Pro nalezení odpovědí hledaných v rámci kroků 'hodnocení' i 'analýzy' jsou využity publikované zdroje k daným nástrojům, primárně pak dokumentace. Avšak platí, že tato analýza se nezabývá zdroji o nástrojích, ale nástroji samotnými. To znamená, že například v následující podkapitole 'Hodnocení zdrojů k analýze' jsou vnímány jako hodnocené zdroje samotné nástroje, nikoliv zdroje o nástrojích, ačkoliv právě ve zdrojích o jednotlivých nástrojích budou hledány odpovědi při prováděném hodnocení, není však prováděno žádné dodatečné systematické prohledávání či hodnocení dostupných zdrojů o nástrojích. Bylo tak rozhodnuto poněvadž je předpokládáno, že v rámci na webu dostupných informací o analyzovaných nástrojích, jakožto jasně definovaném softwaru, není významná šance, že by nalezené informace obsahovaly vyloženě nepravdivá tvrzení, zejména pak pokud budou při odpovídání upřednostněny oficiální zdroje k danému nástroji.
#### Výběr zdrojů
Co se prvotního výběru zdrojů (v tomto případě SW nástrojů využitelných jako uložiště báze znalostí) týče, ten je proveden bez rozsáhlejšího vhledávání, protože limitovaný rozsah práce neumožňuje adekvátní zpracování většího objemu variant zároveň spolu s dosažením stanoveného cíle. Konkrétní předvybraní zástupci posuzovaných datových struktur proto byly již, i s argumentací pro jejich výběr, představeni dříve v této kapitole. A protože i specifický účel pro analýzu byl vyjasněn, následující podkapitola se bude zabývat rovnou hodnocením předvybraných zdrojů a určením pro jakou podmnožinu ze SW kandidátů budou následně v rámci 'analýzy obsahu' zjišťovány odpovědi na stanovené analytické otázky.
#### Hodnocení zdrojů (sw)(čtení, zápis)
V této části budou všichni SW kandidáti vahodnoceni ze dvou hledisek (možnosti zápisu a čtení uložených dat) odvozených z cíle práce (viz. Cíl). Každé z obou hledisek přitom bude vyhodnoceno zvlášť. To znamená, že jejich vyhodnocení vyprodukuje dvě sady výsledků, jednu pro každé hledisko.
##### Hodnocení nástrojů z hlediska zapisování 
Podmínka pro zápis říká, že navržená báze má zachovat úroveň uživatelské zkušenosti, jako poskytuje aktuální řešení. Tím jsou gDocs, případně gSheets pro data jako seznam členů. K ani jedné z této variant, nepotřebuje uživatel téměř žádné nestandartní znalosti k tomu, aby informace zaznamenal. Pokud mu bude dán odkaz na dokument do kterého má zápis udělat, a pod jaký nadpis, mělo by to stačit každému. Jako kritérium pro vyhodnocení kandidátů z hlediska zápisu proto bude, zda vyžadují od uživatele znalost, jako například specifický jazyk k tomu, aby mohl zapisovat do uložiště. Pokud ano, nejsou pro návrh z hlediska zapisování do báze přijatelné.

Výsledkem tohoto hodnocení může být více nástrojů, jelikož není z pohledu cíle práce zapotřebí specifikovat jiná kritéria, než to jedno aktuálně definované.
##### Hodnocení nástrojů z hlediska čtení 
- [ ] možná mírně rozvést nejkratší věty a dovysvětlit jejich význam [chap::hodnocení nástrojů - čtení]

Z hlediska čtení, respektive možností prohledávání uloženého obsahu. Podmínka z cíle říká, že čtení má být efektivní. Měřeno rychlostí na získání výsledků a správností výsledků. To znamená absenci jak chyb kdy je zobrazen výsledek neobsahujicí hledaný obsah (false positive), tak chyb kdy obsah hledaný uživatelem není nalezen, ikdyž ve skutečnosti je zaznamenán a měl by se zobrazit (false negative). Z kandidátu tedy budou vyřazeni ti, kteří toto nesplňují.

Pro zbývající pak bude vyhodnoceno stanovené kritérium příjemnosti využití. Definované jako co nejnižší bariera pro nové uživatele, kterou potřebují překonat aby mohli bázi prohledávat. Velikost bariéry pak bude měřena počtem znaků potřebných pro zadávání dotazů. A podle toho, zda k interakci s bází je v základu k dispozici webové grafické rozhraní.

Zbývající kandidáti tedy budou porovnání podle počtu znaků vyžadovaných k napsání dotazu, přítomnosti webového grafického rozhraní ve výchozí instalaci báze. Vyhodnoceno bude nejdříve pořadí kandidátů podle každého z těchto dvou kritérií zvlášť. Následně takto získané ~~tři~~ hodnoty pro kaďého z kandidátů budou sečteny a kandidát, který bude mít nejnižší výsledné číslo, protože se například podle každého kritéria umístnil na prvním místě, bude přijat jako možná část navrhované báze. 

Výsledkem tohoto hodnocení je tak jediný nástroj, který podle sečtených výsledků z vyhodnocení kritérií hlediska zapisování (rychlost, správnost, příjemnost) vychází jako ten nejlepší.
#### Analýza vybraných zdrojů (sw)(uložení-DS,přístup-PA)->(zdroje vyžadované na údržbu)
Pro zdroje splňující alespoň jedno hledisko hodnocení, jsou určeny jejich 'vnitřní datová struktura', spolu s jejich 'integrovatelností'. 
'Vnitřní datovou strukturou' je myšlena struktura souborů skutečně uložených na disku. To znamená, že může být využita analytická otázka "Jak daný sw ukládá zaznamenané údaje na disk?".
Pojmem 'integovatelnost' jsou pak  varianty skrze které je možné programově přístupovat k uloženému obsahu i ho stejným způsobem modifikovat. Odpovídající analytická otázka proto může být "Jaké možnosti programového přístupu k zaznamenaným údajům daný SW nástroj nabízí?".
A co se 'programového přístupu' týče, typickými příklady jsou například podpora prohledávání databáze pomocí HTTP dotazů, nebo s využitím programovacího jazyka s využitím některé dostupné, na volbě jazyka závisející, specifické knihovny implementující metody pro komunikaci. V obou případech se každopádně jedná o způsoby externí komunikace optimalizované pro využití v kódu konkrétního programu, proto zvolené označení.
#### Získání nejlepších praktik pro modelování dat v nejlépe prohledatelném nástroji
Navíc pro vyhodnocený nejlepší nástroj z hlediska možností čtení uloženého obsahu budou identifikovány nejlepší praktiky pro strukturování do něj ukládaných dat. Tento krok analýzy je důležitý z toho důvodu, že samotný výběr nástroje nezaručuje jeho správné využití a tím pádem nejvyšší šanci na splnění požadavků zohledňovaných při jeho výběru. 
Důvodem pro identifikaci nejlepších postupů pouze pro konkrétně jeden nástroj je to, že primární nedostatky aktuálního řešení jsou právě v možnostech prohledávání uložených záznamů, a proto práce klade důraz zejména na zdokonalení tohoto aspektu znalostních bází. V důsledku takto stanovených priorit a opět vzhledem k limitovanému rozsahu práce, je navrhována struktura pouze pro uložiště s nejlepšími výsledky z hlediska čtení, ikdyž v rámci návrhu bude pro dosažení Cíle práce využito více než jedno uložiště.
#### Interpretace výsledků (sw)
Vycházeje z výsledků, získaných vyhodnocením předchozích dvou analytických otázek, bude určeno, zda je možné na základě vybraných sw kandidátů možné postavit bázi, která jak specifikuje cíl práce, nebude vyžadovat víc prostředků na provoz a údržbu než sama ušetří. To konkrétně bude provedeno pomocí nalezení způsobu jak eliminovat potřebu na ručně vykonávanou údržbu konzistence a aktuálnosti uloženého obsahu v bázi. 
Při tomto hledání je vycházeno z předpokladu, že báze může ušetřit nějaký čas svým využitím, jen když nebude zároveň také vyžadovat čas na údržbu pro svojí správnou funkčnost. Rovněž by také neměla vyžadovat žádné finanční prostředky, jelikož vzhledem k neziskové povaze skauta není způsob, jak by se prostředky vydané na provoz takového systému mohly vrátit.
Základní otázkou, kterou se tedy tento krok analýzy bude snažit zodpovědět je otázka "Je možné eliminovat či alespoň zcela minimalizovat potřebu lidských i finančních zdrojů na údržbu konzistence údajů ve vybraných softwarech zaznamenaných?".

V případě nalezení takového způsobu, bude způsob popsán a následně sestaven výčet funkcionalit kritických pro funkcionalitu odpovídající požadavkum na navrhovanou bázi.

#### Výstupy
- [ ] DODĚLAT [chap::analyza sw.výstupy]

tool UI w (Data Structure, programmatic access)
tool UI r (Data Structure, programmatic access)
sw solution description (best practices for DB data structuring, core functionalities, proč jenom DB a ne Docs Schema?)

### Schema
![[../assets/analyzaswkandidatu-metodika-UMLactivity.jpg]]
## Metodika analýzy existujících bází
#### Účel postupu
Motivací pro tuto sekci je druhý kritický aspekt navrhované báze. Jedná se však pouze o aspekt druhý v pořadí prezentace, nikoliv druhý ve významu důležitosti pro návrh. Ve skutečnosti je tento aspekt pro návrh na podobné úrovni důležitosti jako ten řešený v předchozí sekci. 
Jak už bylo zmíněno, je tímto aspektem určení samotného obsahu, který bude v bázi uložený. Proto byl stanoven **dílčí cíl:** "Vybrat výseč reality relevantní pro skautské programy.". Cílem této části proto je vybrání pojmů a jejich vztahů, kteréžto budou představovat odpověď na otázku "Co zaznamenávát v navrhované bázi?"

Záměrem však není ani tak provedení vyčerpávající analýzy dané domény, jelikož to by važadovalo celou samostatnou práci, jako spíš snaha o agregování pohledů na problematiku několika existujícími bázemi. Výsledky provedeného postupu tak umožňují tvorbu báze, která dovede odpovídat na rozsáhlejší sadu odpovědí, než báze existující. A zároveň v důsledku tohoto postupu je možné rozšiřovat navrženou bázi obsahem z těch existujících, protože možný obsah dané báze byl zohledněn při návrhu a zakomponován do výsledného schematu báze.
#### Obecný postup
Pro získání odpovědi na otázku "Co zaznamenávat v bázi skautských programů?", byla opět využita 'analýza literatury' ([[../../myDM/Zotero/LiteratureNotes/berndtssonThesisProjectsGuide2008]]), stejně jako v první provedené analýze.

- [ ] MOŽNO doplnit konkrétní specifika standartu UML
- [x] DOPLNIT popsanou odchylku od standartního UML
Navíc bylo v rámci kroku interpretace výsledků využito UML. Nástroj byl vybrán jelikož velmi dobře standartizuje způsoby modelování struktur i skutečnosti obecně. Ve verzi 2.5.1 ze které aktuálně výcházím, má i celou druhou polovinu zaměřenou na stavy, chování, akce interakce, až případy užití. Ač se jedná o velmi užitečnou část, na její využití v této práci pravděpodobně nedojde z důvodu času a rozsahu práce.
Jediná odchylka od standardu UML bude provedena v případě generalizace, která místo běžné verze:
![[myDM/Zotero/LiteratureNotes/UnifiedModelingLanguage#^N57FEDGRaIAQSHBP8p145]]
bude pro generalizace využívat následující notaci.
[]
Je tak učiněno z toho důvodu, že v používaném modelovacím nástroji (draw.io) je jednoduší s modelem manipulovat (posouvat jednotlivé části) v případě využití alternativní notace pro modelování generalizací.
### Konkrétní postup
#### Výběr
Podobně, jako při předchozí analýze, nebylo opět provedeno žádné systematické prohledávání dostupných bází, nýbrž byly vybrány báze, které bývají občas, minimálně našem v oddíle, využívány jako inspirace pro přípravu realizovaných programů v rámci naší činnosti.

První z existujících bází je webová stránka 'chystamprogram.skaut.cz', jenž byla vytvořena organizací Junák - český skaut, která zároveň za celý obsah zcela zodpovídá. [[../../myDM/Zotero/LiteratureNotes/ChystamProgramOProjektu#^NMC5UM33aSNYTTS96]] 

Druhou analyzovanou bázi pak představuje 'Velká encyklopedie her'. Ta je tvořena čtyřmi samostanými tituly vydanými mezi lety 1987-1988, napsanými panem Milošem Zapletalem. [ ] Jak už název napovídá, jeji zaměření je čistě na hry, které jsou nepochybně také součástí skautských programů, těm se nicméně věnuje velmi podrobně. Slovo "Velká" v názvu totiž nijak zvlášť nepřehání. Každá z knih má v průměru přibližně 600 stran, sice menšího formátu, ale i přesto se často vejdou i dvě hry na stránku.

Za existující bázi by se daly považovat i zápisy, které byly skutečně vytvořeny a využity při přípravě konkrétních dříve realizovaným programům na sdíleném disku našeho oddílu. 
Systematická analýza tohoto zdroje by sice byla vzhledem k nesystematicky strukturovaným zápisům poměrně komplikovaná. Avšak pohled na zkoumanou problematiku touto bází je cenný, protože reprezentuje údaje, které jsou pro skautské programy považovány za důležité cílovími uževitali navrhované báze. Proto aby bylo možné při návrhu zohlednit i pohled na problematiku očima cílových uživatelů navrhovaného systému, byla tato bále ponechána ve výběru.
#### Hodnocení 
Co se kvality a vhodnosti pro potřeby práce týče, představují existující báze zcela optimální zdroje k analýze.
Hodnocení zdrojů proto nesloužilo v tomto případě, k vybrání jejich podmnožiny pro další zpracování, jako v předchozí analýze. Nicméné stále mělo smysl vybrané zdroje ohodnotit. Konkrétně ze dvou důvodů, zaprvé proto, aby byly představeny kvality bází, které zároveň argumentují jejich výběr. Zadruhé pak proto, aby byly představeny jejich nedostatky, které je čiňí nepřijatelnými či nevhodnými pro takové využití, jako by měla umožnit v této práci navržená báze. 
#### Analýza 
Cílem analýzy obsahu vybraných zdrojů pak bylo pro každý z nich zvlášť, zodpovědět následující analytické otázky.
- Jaké pojmy (max 2) nejlépe vystihují obsah dané báze?
- Jaké pojmy jsou využity danou bází k charakterizování zapsaných aktivit?
- Podle jakých pojmů umožňuje daná báze prohledávat? //(-> Kompetenční otázky)

- [ ] DOPLNIT postup pro definování kompetenčních otázek [chap::metodika] [sect::analýzaBází]

S vyjímkou sdíleného disku našeho oddílu, který byl do výběru zařazen z důvodu své cennosti, avšak neumožňuje tak snadné systematické vyhodnocení jako zbylé dvě báze, kvůli své "chaotičtější" struktuře, v jehož případě jsou vyhodnoceny pouze první dvě z analytických otázek.

Vzhledem k rozdílným strukturám analyzovaných bází, budou odpovědi na otázky v každěm případě získány lehce odlišným způsobem.
 
Nejsnažší zodpovězení umožňuje báze chystamprogam, jelikož poskytuje šablonu pro nové záznamy s pojmenovanými a popsanými políčky(prvky) k vyplnění. 
Odpověd na první otázku je proto získána vypsáním názvů,jejich popisů, případně povolených hodnot pro všechny možné prvky ze šablony. 
K zodpovězení druhé jsou pak prohledýny poskytnuté filtry ve vrchní části stránky 'Hledat Aktivity' v této bázi a vypsány pojmy použité jako názvy parametrů umožňujících filtrování, stejně tak jejich přípustné hodnoty.

V případě tištěné encyklopedie je trochu problém, protože zápisy v ní nejsou na první pohled nijak systematicky strukturovány, kromě symbolického značení vedle názvů a svého zařazení do kapitol. Bylo by proto potřeba vybrat vzorek ze záznamů a na základě něj se pokusit určit jaká části se napříč záznamy vyskytují. Naštěstí jedna z encyklopedií zahrnuje ve své Úvodní kapitole část pojmenovanou "Jak zapisovat tradiční hry". Autor se v ní sice věnuje takzvaně tradičním dětským hrám. Tím má na mysli hry, které si děti hrají, ale jejich pravidla existují pouze jako sdílené vědomosti mezi hráči, nejsou však nikde popsána, tudíž je šance, že postupem času tyto hru upadnou v zapomění. Ač se autorova motivace liší od motivace této práce. Výčet parametrů relevantních pro hry, které v této části nabízí, představuje podobně hodnotný zdroj, jako šablona pro zapisování v předchozí bázi. Pro získání odpovědi na první analytickou otázku proto budou vypsány pojmy právě z tohoto výčtu, nikoliv ze skutečně zapsaných her. 
Co se prohledávání týče, to je zprostředkováno samotnými knihami, jejich kapitolami a symbolickým značením, u jednotlivých záznamů, popsaným za začátku každé z knih. Proto právě z těchto částí by bylo vhodné získat odpovědi na druhou z analytických otázek. Kapitoly avšak, vzhledem ke značému rozsahu encyklopedie, obsahují příliš mnoho pojmů na to, aby je bylo možné, v rámci limitovaného rozsahu této práce, adekvátně systematicky vyhodnotit a nezanedbat v důsledku toho další klíčové části práce. Proto v rámci analýzy encyklopedie her, k zodpovězení druhé analitické otázky, bude použito pouze symbolické značení u jednotlivých her.

Aby bylo možné vyhodnocení sdíleného disku, byla nejprve provedena stručná rešerše obsahu na něm uloženého. A na základě této rešerše jsou pak určeny odpovědi na první dvě analytické otázky.
#### Interpretace
Výsledky z analýzy, ve formě dlouhého seznamu pojmů, by se při návrhu schématu báze jistě zužitkovaly, nejedná se však o příliš efektivní ani elegantní řešení.
Pro vytvoření koherentního celku z právě zmíněného obsáhlého seznamu, čárkou nebo novým řádkem oddělených pojmů, byl proto při návrhu využit diagram tříd. Který byl sestaven s pomocí získaných pojmů, mých doménových znalostí, jakožto člena oddílu posledních 15 let, zároveň jako vedoucího posledních 6 let a s pomocí následujícího postupu.
##### Základní definice
Nejdříve byly určeny vztahy mezi obsahem z jednotlivých existujících bází. Jelikož každá z nich se na problematiku skautských programů dívá z jiného pohledu, agregací těchto pohledů by měla vzniknout lepší a přesnější základní definice skautských programů, než v případě využití pouze jedné báze. Pro její získání byly využity základní pojmy, charakterizující obsah jednotlivých bází, získané předchozím krokem.

Získané základí pojmy a jejich vztahy jsou vymodelovány pomocí jednoduchého, ale pravdivého diagramu tříd, který tak poskytne základní strukturu tvořeného diagramu. 

S tím, že tento základní prvek, bude v následujím postupu tvorby diagramu obohacován a doplňován pojmy získanými literární analýzou.
##### Rozšíření definice
Cílem nyní bylo vhodně asociovat získané pojmy k základním třídám, zvoleným jako reprezentace domény skautských programů.
###### Možné asociace
Prvním krokem, provedeným pro určení 'vhodného' způsobu asociace získaných pojmu na základní struktru, bylo jejich rozřazení do skupin podle toho, k jaké základní třídě se obvykle ve skutečnosti vážou a mohou vázat. 
Zároveň jelikož již byly určeny konkrétní vztahy mezi jednotlivými základními pojmy, potažmo obsahem jednotlivých bází, bylo určování možné asociovatelnosti daného pojmu s konkrétní základní třídou značně zjednodušeno.
Zjednodušení vyplývá ze základního modelu tak, že díky němu je zřejmé, že postačí například pro pojmy ze sdíleného disku, reprezentujícího záznamy o událostech, vyhodnotit pouze možnou asociovatelnost s pojmem Aktivita, protže to je v generalizační struktuře jeho "sourozenec". Je tomu proto, že pokud možnost asociace daného pojmu, z báze primárně událostí, eistuje. Znamená to automaticky, že Hra, jakožto "potomek" aktivity, je také Aktivita, a není třeba dále posuzovat zda se pojem z báze událostí může asociovat i s hrami. Zároveň pak to znamená i to, že daný pojem může být převeden do vlastnictví třídy Program, která je "rodičem" jak aktivit, tak událostí.

Z aplikování právě popsané logiky pak vyplývá následující postup pro rozřazení, nikoliv skutečnému modelování asociace, ke konkrétním základním třídám.

K určení, analýzou získaných, pojmů asociovatelných se třídou Program, byly výsledky vybrány z jednotlivých bází podle následujících pravidel:
 - z chystamprogram, asociovatelné i s událostmi
 - z popisu obsahu sdíleného disku, asociovatelné i s aktivitami
 - z encyklopedie her, asociovatelné s uálostmi i s aktivitami

Jelikož už ze získaných pojmů byly vybrány ty, které se dají asociovat i s událostmi, nebylo třeba ten vztah dále zvažovat. K určení pojmů asociovatelných se třídou Aktivita, byly tedy výsledky vyrány podle pravidel:
 - z chystamprogram, bez pojmů přiřazených programu
 - z encyklopedie her, asociovatelné i obecněji s aktivitami, bez pojmů přiřazených programu

K určení pojmů asociovatelných se třídou Hra tak byly vybrány podle pravidla:
 - z encyklopedie her, bez pojmů přiřazených programu, bez pojmů přiřazených k aktivitě

Obdobně k určení pojmů ke třídě Událost, byly vabrány podle pravidla:
 - z popisu obsahu sdíleného disku, bez pojmů přiřazených programu

###### Asociovaná struktura
Jelikož se mezi získanými pojmy vyskytovyly již existující struktury a naopak některé skupinky pojmů byly až příliš specializované na to, aby bylo vhodné je asociovat přímo na základní třídu, byly provedeny následující kroky, mimo jiné také pro minimalizaci počtu tříd, jenž bylo třeba napojovat.

První hledanou existující strukturou byly třídy jako například 'oblast rozvoje' a ' podoblast rozvoje', jenž zahrnují jeden třídu, představující generalizaci tříd zbývajících, které tak jsou jeho specializacemi. Rovněž byly hledány skupiny tříd jako například 'věk skupiny' a 'velikost skupiny', které mezi pojmy z analýzy žádný generalizovaný protějšek nemají. 
V takových případech záleželo na tom, zda je pro přiřazenou základní třídu "důležité umět rozlišovat" mezi jednotlivými třidami v nalezených skupinkách či nikoliv, a je tak možné zobecnit (generalizovat) celou skupinku jedinou třídou. 
Příkladem situace, kdy je pro základní třídu důležité umět rozlišovat mezi jednotlivými třídami a generalizování by tak nefungovalo příliš dobře, jsou třeba právě již zmíněné pojmy 'věk skupiny' a 'velikost skupiny'. V důsledku jejich zobecnění, třeba třídou 'charakteristika skupiny' a jeho asociací k základní třídě místo dvou separátních asociací k nyní specializovaným třídám, by měla základní třída totiž možnost reprezentovat hodnoty z generalizované třídy pouze jako charakteristiky, a byl by tak ztracen význam jednotlivých hodnot.
Proto v situacích jako tato bylo využito místo toho kompozice. To znamená, že pro třídy z dané skupinky tříd s podobným významem byla vytvořena nová třída, která vlastní podobné třídy jako atributy.

Nakonec pak z existjících struktur byly vyhledány a vymodelovány povinné asociace mezi třídami přiřazeným k těm základnim. Jelikož i tyto mohou snížit počet tříd nutných asociovat k těm základním v případě, kdy například dvě třídy jsou asociovány mezi sebou ('charakteristický okamžik', 'dokumentární fotografie'), a jedna z nich (dokumentární fotografie) se do výběru dostala proto, že je primárně silně asociována s druhou z nich, která však už klidně může být asociována i k základní třídě.
###### Vhodná asociace
Díky struktuře vytvořené mezi třídami, jejichž asociaci k těm základním byla určována, bylo možné určit, které z nich je třeba explicitně asociovat k odpovídající základní třídě.  A které třídy naopak nepotřebují, protože jsou specializací nebo částí některé jiné, která sdružuje více podobných tříd a jako jediná má tak explicitně vymodelovanou asociaci s odpovídající základní třídou. 
Zbývalo tedy už jen určit jak konkrétně má být vymodelována asociace mezi základními třídami a jim přiřazeným, teď již strukturovaných, třídám. Možnými variantami, vzhledem ke standartu UML, byly buď jako atribut (vlastnost) dané základní třídy nebo jako separátní třídu, která je s tou první asociována. Toto rozhodování bylo provedeno na základě "síly" konkrétního asociačního vztahu s tím, že silné závislosti jsou modelovány jako atributy daných základních tříd a slabé závislosti jsou modelovány separátními oddělenými třídami. Podle čeho ale vyhodnotit onu sílu asociací?

Ve statistice je například míra asociace určována pro numerické proměnné tím, jak často se konkrétní hodnoty jednotlivých proměnných vyskytují spolu. Dalo by se také říci, že nejsilnější je takový vztah, který je povinný a vyskytuje se proto vždy. podobně V této práci je za silnou asociace považová tehdy, pokud se vyskytuje u většiny instancí konkrétní třídy. Opačně v případě, kdy bývá uvedena jen občas, je považována za slabou. 
Samotné rozhodnutí pak bohužel nebylo z důvodu rozsahových možností práce založeno na žádných jiných podkladech, než mych doménových znalostech a informacích z původně analyzovaných bází. V důsledku toho, odpovídá volba tříd k asociaci jako atributy, pravděpodobně více mému vlastnímu přesvědčení o tom která třída je pro dané záznamy nejužitečnější a tudíž by bylo nejlepší klást důraz na její zaznamenávání, než podle skutečných frekvencí výskytu ku celkovému počtu záznamů. 

Obdobně byla nakonec vyhodnocena i takzvaná 'násobnost' vztahů, která udává zda instance třídy A mohou být asociovány s více než jednou instancí z třídy B.
Volitelnost (instance z třídy A musejí být asociovány s instancí z třídy B) vztahů nebyla vyhodnocena, protože je vycházeno z předpokladu, že všechno zapisování do báze je dobrovolná aktivita (jako vše ve skatu), tudíž nebudou zápisy vynucovat zapsání žádné ze svých částí a všechny asociované třídy jsou proto volitelné.
Navíc jisté zohlednění "povinnosti" k zapsání konkrétních částí bylo učiněno v předchozím kroce v rámci určování síly asociace.
#### Výstupy
##### hodnocení exist. bází
- [x] DOPLNIT popsat výstupy 'hodnocení zdrojů' z postupu analýzy bází
 Výsledky z hodnocení jednotlivých analyzovaných bází, argumentující jejich výběr silnými stránkami jejich obsahu a zároveň se zdůvodněním, proč není využívána daná existující báze, ale je navrhována nová, se nachází ve druhé sekci kapitoly Teorie.

##### analýza obsahu bází
- [x] DOPLNIT popsat výstupy 'analýzy obsahu z postupu analýzy bází

Co se prezentování analýzou získaných pojmů týče, to je uskutečněno pomocí jediného seznamu. Nejedná se však pouze o spojené získaných dílčích výsledků dohromady. Primárním účelem této prezentace je totiž, mimo transformace získaných údajů s ohledem na čtenáře, rovněž také předzpracování a vyčištění analýzou získaných dat, než jsou předány dále k jejich interpretaci.
Důvodem pro toto předzpracování je třeba i to, že některé pojmy jsou v množném a jiné v jednotném čísle a pro účely následné interpretace je žádoucí mít všechny pojmy v čísle jednotném, ale především skutečnost, že různé báze mohou používat stejné výrazy, ale myslet odlišný význam a naopak. Příkladem může být 'místo konání'. V bázi chystamprogram tento pojem může reprezentovat hodnoty npř. místnost, louka,... . Zato v případě asociace s událostí jsou tímto pojmem typicky označovány přibližné i konkrétní geografické lokace, kde se děti s vedoucími budou v průběhu události pohybovat, případně nocovat, pokud se jedná o vícedení událost. Místem konání pro události tak bývají například konkrétní skautské klubovny, souřadnice tábořiště etc.. 

Nestačí proto vybrat pouze pojmy, které se opakují, nýbrž bylo zapotřebí zjistit, co daným pojmem báze zastupuje, respektive jaké konkrétní hodnoty pojem v daném kontextu reprezentuje. 
Ke každému pojmu v seznamu proto bude doplněn krátký popis jeho významu odvozený z kontextu ve kterém se nachází v bázi ve které byl nalezen. Právě z umístnění v konkrétní bázi vyplývá i další část údajů, jenž budou zachyceny o každém pojmu ve vytvořeném souhrnném seznamu. Aby transformací dat nebyla ztracena informace o původním místě výskytu daného pojmu, jsou v řádku za názvem pojmu a pomlčkou uvedeny zkratky bází ze kterých byl pojem získán. Zároveň v případě, kdy báze explicitně identifikuje sadu konkrétních hodnot, jenž jsou pojmem reprezentovány, jsou pro takový pojem v prezentovaném seznamu hodnoty z dané sady uvedeny.
Z výsledků analýzy, které zatím nemají specifikovaný formát prezentace, zbývají už tak jen údaje o tom, které pojmy byly vybrány jako základní a které ve své původní bázi zprostředkovávají filtrování obsahu báze podle svých hodnot. Základní pojmy, jelikož jich je relativně málo vzhledem k celku seznamu, jsou označeny symbolem šipky "==>>" v prvním řádku záznamu před jejich názvem. A v případech, kdy je podle pojmu a jím reprezentovaných hodnot možné prohledávat obsah báze v níž se vyskytuje, je záznam v souhrnném seznamu rozšířen symbolickou předponou dvou otazníků "??" a do třetího řádku záznamu pod řádek s popisem je doplněna otázka, kterou daný pojem umožňuje bázi zodpovídat.
- [x] zbývající údaje které byly získány zbývá už jen
- [x] x -> jednotné číslo x

##### interpretace
Výsledky interpretace, uvedené na začátku praktické části, prezentují postupné rozšiřování modelu pro základní pojmy a získání tak agregovaného pohledu na zkoumanou doménu.

Toho je docíleno zaprvé tak, že jsou nejdříve představeny výsledky z dílčího kroku 'zakreslení pojmů' ve formě modelu, jenž má pouze umístněné zakreslené pojmy v blízkosti základních pojmů, avšak neobsahuje zatím žádné asociace.  
S jedinou vyjímkou atributů základních tříd, jejichž datovým typem je buď boolean nebo intager, ty jsou totiž již při zakreslování umístněny "dovnitř" odpovídající základní třídy. Bylo tak učiněno z důvodu lepší přehlednosti modelu. Konkrétně byl postup vybrán jakožto nejsnažší možnost na "zbavení se" části pojmů, rychle, hned na začátku, pomocí snadno vyhodnotitelného kritéria a usnadnění tak celého dalšího modelování.

A zadruhé, jsou prezentovány výsledky z kroku 'modelování pojmů'. Není však představen celý model najednou, nýbrž jsou představený postupně dílčí pohledy, na část vytvořeného modelu odpovídající jendotlivým základním třídám, počínaje od té nejvíce generalizované.  
Pro každý z těchto dílčích pohledů na model je následně poskytnut podrobný popis vyseče reality, který je jím zobrazen. Zároveň je také doručena argumentace pro jednotlivá rozhodnutí, učinněná v rámci procesu modelování pojmů, a tím tak odůvodněno, proč jsou konkrétní pojmy vymodelovány tak jak jsou vymodelovány a ne jinak.
- [ ] AKTUALIZOVAT model pojmů výstupy
### Schema
![[../assets/analyzadomenyskautskychprogramu-metodika-UMLactivity.jpg]]
## Metodika tvorby DB schematu
#### Účel postupu
**Dílčí cíl:** Navrhnout schema pro databázi.
#### Obecný postup
### Konkrétní postup
#### Výstupy
### Schema
![[../assets/tvorbadbschematu-metodika-UMLactivity.jpg]]
## Metodika ověření výsledků
#### Účel postupu
#### **Dílčí cíl:** Ověřit úspěšnost dosažení výsledků
#### Obecný postup
### Konkrétní postup
#### Výstupy
### Schema
![[../assets/overenivysledku-metodika-UMLactivity.jpg]]

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

## Metodika návrhu
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





