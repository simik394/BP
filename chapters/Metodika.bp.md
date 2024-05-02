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
Členění práce je provedeno podle doporučené struktury pro výzkumné práce IMRaD [ ].

První následující kapitolou je proto Metodika, která s využitím výše uvedeného schématu definuje metody využité pro dosažení stanovených dílčích cílů. 
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

### schema full %% fold %% 
Následující schéma, založené na notaci 'activity' z UML, reprezentuje strukturu této práce. Jsou v něm zobrazeny datové objekty(obdélníky) a aktivity(čtyřúhelníky se zaoblenými rohy). ...
- [ ] Doplnit podrobnější vysvětlení čtení použité notace 

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
- [ ] možná mírně rozvést nejkratší věty a dovysvětlit jejich význam [chap::Metodika] [sect::hodnocení nástrojů - čtení]

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
- [x] DODĚLAT [chap::analyza sw.výstupy]
Výsledky z dosažení prvního dílčího cíle jsou prezentovány jako první v kapitole Teorie.
S tím že pořadí prezentace odpovídá pořadí jejich vypracování. Nejdříve jsou proto uvedena hodnocení SW kandidátů podle hledisek možností čtení a psaní, čímž je argumentován následný výběr jejich podmnožin podle specifikovaných hledisek.
Pro vybrané kvalifikované kandidáty jsou v další části vyhodnoceny charakteristiky uložení dat v daných softwarech a možnosti programového přistupování k jejich obsahu.
Po těchto, následuje posouzení dosažitelnosti cíle prací stanoveného a prezentování potenciálního řešení softwarové infrastruktury pro navrhovanou bázi. Samotná dosažitelnost je přitom charakterizována sadou požadavků, které musí být splněny, aby návrh bylo možné skutečně postavit, 
Rovněž jsou uvedeny nejlepší praktiky pro modelování dat v nástroji, jenž byl v rámci této metody vyhodnocen jako nejlepší v nabízených možnostech čtení v něm uloženého obsahu.


## Metodika analýzy existujících bází

#### Účel postupu
Motivací pro tuto sekci je druhý kritický aspekt navrhované báze. Jedná se však pouze o aspekt druhý v pořadí prezentace, nikoliv druhý ve významu důležitosti pro návrh. Ve skutečnosti je tento aspekt pro návrh na podobné úrovni důležitosti jako ten řešený v předchozí sekci. 
Jak už bylo zmíněno, je tímto aspektem určení samotného obsahu, který bude v bázi uložený. Proto byl stanoven **dílčí cíl:** "Vybrat výseč reality relevantní pro skautské programy.". Cílem této části proto je vybrání pojmů a jejich vztahů, kteréžto budou představovat odpověď na otázku "Co zaznamenávát v navrhované bázi?"

Záměrem však není ani tak provedení vyčerpávající analýzy dané domény, jelikož to by važadovalo celou samostatnou práci, jako spíš snaha o agregování pohledů na problematiku několika existujícími bázemi. Výsledky provedeného postupu tak umožňují tvorbu báze, která dovede odpovídat na rozsáhlejší sadu odpovědí, než báze existující. A zároveň v důsledku tohoto postupu je možné rozšiřovat navrženou bázi obsahem z těch existujících, protože možný obsah dané báze byl zohledněn při návrhu a zakomponován do výsledného schematu báze.

#### Obecný postup
Pro získání odpovědi na otázku "Co zaznamenávat v bázi skautských programů?", byla opět využita 'analýza literatury' ([[../../myDM/Zotero/LiteratureNotes/berndtssonThesisProjectsGuide2008]]), stejně jako v první provedené analýze.

- [ ] [Ttyp::VYLEPŠIT]|: #p/bp/metodika/báze/obecnýPostup - MOŽNO doplnit konkrétní specifika standartu UML 
- [x] DOPLNIT popsanou odchylku od standartního UML
Navíc bylo v rámci kroku interpretace výsledků využito UML. Nástroj byl vybrán jelikož velmi dobře standartizuje způsoby modelování struktur i skutečnosti obecně. Ve verzi 2.5.1 ze které aktuálně výcházím, má i celou druhou polovinu zaměřenou na stavy, chování, akce interakce, až případy užití. Ač se jedná o velmi užitečnou část, na její využití v této práci pravděpodobně nedojde z důvodu času a rozsahu práce.
Jediná odchylka od standardu UML bude provedena v případě generalizace, která místo běžné verze:
![[myDM/Zotero/LiteratureNotes/UnifiedModelingLanguage#^N57FEDGRaIAQSHBP8p145]]
bude pro generalizace využívat následující notaci.
[]
Je tak učiněno z toho důvodu, že v používaném modelovacím nástroji (draw.io) je jednoduší s modelem manipulovat (posouvat jednotlivé části) v případě využití alternativní notace pro modelování generalizací.

### Konkrétní postup

#### Výběr (báze)
Podobně, jako při předchozí analýze, nebylo opět provedeno žádné systematické prohledávání dostupných bází, nýbrž byly vybrány báze, které bývají občas, minimálně našem v oddíle, využívány jako inspirace pro přípravu realizovaných programů v rámci naší činnosti.

První z existujících bází je webová stránka 'chystamprogram.skaut.cz', jenž byla vytvořena organizací Junák - český skaut, která zároveň za celý obsah zcela zodpovídá. [[../../myDM/Zotero/LiteratureNotes/ChystamProgramOProjektu#^NMC5UM33aSNYTTS96]] 

Druhou analyzovanou bázi pak představuje 'Velká encyklopedie her'. Ta je tvořena čtyřmi samostanými tituly vydanými mezi lety 1987-1988, napsanými panem Milošem Zapletalem. [ ] Jak už název napovídá, jeji zaměření je čistě na hry, které jsou nepochybně také součástí skautských programů, těm se nicméně věnuje velmi podrobně. Slovo "Velká" v názvu totiž nijak zvlášť nepřehání. Každá z knih má v průměru přibližně 600 stran, sice menšího formátu, ale i přesto se často vejdou i dvě hry na stránku.

Za existující bázi by se daly považovat i zápisy, které byly skutečně vytvořeny a využity při přípravě konkrétních dříve realizovaným programům na sdíleném disku našeho oddílu. 
Systematická analýza tohoto zdroje by sice byla vzhledem k nesystematicky strukturovaným zápisům poměrně komplikovaná. Avšak pohled na zkoumanou problematiku touto bází je cenný, protože reprezentuje údaje, které jsou pro skautské programy považovány za důležité cílovími uževitali navrhované báze. Proto aby bylo možné při návrhu zohlednit i pohled na problematiku očima cílových uživatelů navrhovaného systému, byla tato bále ponechána ve výběru.

#### Hodnocení (báze)
Co se kvality a vhodnosti pro potřeby práce týče, představují existující báze zcela optimální zdroje k analýze.
Hodnocení zdrojů proto nesloužilo v tomto případě, k vybrání jejich podmnožiny pro další zpracování, jako v předchozí analýze. Nicméné stále mělo smysl vybrané zdroje ohodnotit. Konkrétně ze dvou důvodů, zaprvé proto, aby byly představeny kvality bází, které zároveň argumentují jejich výběr. Zadruhé pak proto, aby byly představeny jejich nedostatky, které je čiňí nepřijatelnými či nevhodnými pro takové využití, jako by měla umožnit v této práci navržená báze. 

#### Analýza 
Cílem analýzy obsahu vybraných zdrojů pak bylo pro každý z nich zvlášť, zodpovědět následující analytické otázky.
- Jaké pojmy jsou využity danou bází k charakterizování zapsaných aktivit?
- Podle jakých pojmů umožňuje daná báze prohledávat? 
- Jaké pojmy (max 2) nejlépe vystihují obsah dané báze a daly by se tak pro ni označit jako 'základní'?

- [x] DOPLNIT postup pro definování kompetenčních otázek [chap::metodika] [sect::analýzaBází]

S vyjímkou sdíleného disku našeho oddílu, který byl do výběru zařazen z důvodu své cennosti, avšak neumožňuje tak snadné systematické vyhodnocení jako zbylé dvě báze, kvůli své "chaotičtější" struktuře, v jehož případě jsou vyhodnoceny pouze první a poslední analytická otázka.
Vzhledem k rozdílným strukturám analyzovaných bází, byly odpovědi na otázky v každěm případě získány lehce odlišným způsobem.
 
Nejsnažší zodpovězení umožnila báze chystamprogam, jelikož poskytuje šablonu pro nové záznamy s pojmenovanými a popsanými políčky(prvky) k vyplnění. 
Odpověd na první otázku byla proto získána vypsáním názvů, jejich popisů, případně povolených hodnot pro všechny možné prvky ze šablony. 
K zodpovězení druhé pak byly prohledány filtry poskytnuté ve vrchní části stránky 'Hledat Aktivity' v této bázi a vypsány pojmy použité jako názvy parametrů umožňujících filtrování, stejně tak jejich přípustné hodnoty.

V případě tištěné encyklopedie je trochu problém, protože zápisy v ní nejsou na první pohled nijak systematicky strukturovány, kromě symbolického značení vedle názvů a svého zařazení do kapitol. Bylo by proto potřeba vybrat vzorek ze záznamů a na základě něj se pokusit určit jaká části se napříč záznamy vyskytují. Naštěstí jedna z encyklopedií zahrnuje ve své Úvodní kapitole část pojmenovanou "Jak zapisovat tradiční hry". Autor se v ní sice věnuje takzvaně tradičním dětským hrám. Tím má na mysli hry, které si děti hrají, ale jejich pravidla existují pouze jako sdílené vědomosti mezi hráči, nejsou však nikde popsána, tudíž je šance, že postupem času tyto hru upadnou v zapomění. Ač se autorova motivace liší od motivace této práce. Výčet parametrů relevantních pro hry, které v této části nabízí, představuje podobně hodnotný zdroj, jako šablona pro zapisování v předchozí bázi. Pro získání odpovědi na první analytickou otázku proto budou vypsány pojmy právě z tohoto výčtu, nikoliv ze skutečně zapsaných her. 
Co se prohledávání týče, to je zprostředkováno samotnými knihami, jejich kapitolami a symbolickým značením, u jednotlivých záznamů, popsaným za začátku každé z knih. Proto právě z těchto částí by bylo vhodné získat odpovědi na druhou z analytických otázek. Kapitoly avšak, vzhledem ke značému rozsahu encyklopedie, obsahují příliš mnoho pojmů na to, aby je bylo možné, v rámci limitovaného rozsahu této práce, adekvátně systematicky vyhodnotit a nezanedbat v důsledku toho další klíčové části práce. Proto v rámci analýzy encyklopedie her, k zodpovězení druhé analitické otázky, bude použito pouze symbolické značení u jednotlivých her.

Aby bylo možné vyhodnocení sdíleného disku, byla nejprve provedena stručná rešerše obsahu na něm uloženého. A na základě této rešerše jsou pak určeny odpovědi na první a poslední analytickou otázku.

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
Výsledky z hodnocení jednotlivých analyzovaných bází, argumentující jejich výběr silnými stránkami jejich obsahu a zároveň se zdůvodněním, proč není využívána daná existující báze, ale je navrhována nová, se nachází ve druhé sekci kapitoly Teorie.

##### analýza obsahu bází
Co se prezentování analýzou získaných pojmů týče, to je uskutečněno pomocí jediného seznamu. Nejedná se však pouze o spojené získaných dílčích výsledků dohromady. Primárním účelem této prezentace je totiž, mimo transformace získaných údajů s ohledem na čtenáře, rovněž také předzpracování a vyčištění analýzou získaných dat, než jsou předány dále k jejich interpretaci.
Důvodem pro toto předzpracování je třeba i to, že některé pojmy jsou v množném a jiné v jednotném čísle 
- [ ] [Ttyp::DODĚLAT]|[testm::10min]  - nejen v jednotném čísle, ale připravit všestraně na použití v modelu ||: #p/bp/metodika/báze/výstupy 

a pro účely následné interpretace je žádoucí mít všechny pojmy v čísle jednotném, ale především skutečnost, že různé báze mohou používat stejné výrazy, ale myslet odlišný význam a naopak. Příkladem může být 'místo konání'. V bázi chystamprogram tento pojem může reprezentovat hodnoty npř. místnost, louka,... . Zato v případě asociace s událostí jsou tímto pojmem typicky označovány přibližné i konkrétní geografické lokace, kde se děti s vedoucími budou v průběhu události pohybovat, případně nocovat, pokud se jedná o vícedení událost. Místem konání pro události tak bývají například konkrétní skautské klubovny, souřadnice tábořiště etc.. 

Nestačí proto vybrat pouze pojmy, které se opakují, nýbrž bylo zapotřebí zjistit, co daným pojmem báze zastupuje, respektive jaké konkrétní hodnoty pojem v daném kontextu reprezentuje. 
Ke každému pojmu v seznamu proto bude doplněn krátký popis jeho významu odvozený z kontextu ve kterém se nachází v bázi ve které byl nalezen. Právě z umístnění v konkrétní bázi vyplývá i další část údajů, jenž budou zachyceny o každém pojmu ve vytvořeném souhrnném seznamu. Aby transformací dat nebyla ztracena informace o původním místě výskytu daného pojmu, jsou v řádku za názvem pojmu a pomlčkou uvedeny zkratky bází ze kterých byl pojem získán. Zároveň v případě, kdy báze explicitně identifikuje sadu konkrétních hodnot, jenž jsou pojmem reprezentovány, jsou pro takový pojem v prezentovaném seznamu hodnoty z dané sady uvedeny.

Zbývají tak už jen dva údaje z původní datové sady, které zatím nemají specifikovaný formát prezentace, je jím údaj o tom, které pojmy byly vybrány jako základní a které ve své původní bázi zprostředkovávají filtrování obsahu báze podle svých hodnot. Základní pojmy, jelikož jich je relativně málo vzhledem k celku seznamu, jsou označeny symbolem šipky "==>>" v prvním řádku záznamu před jejich názvem. A v případech, kdy je podle pojmu a jím reprezentovaných hodnot možné prohledávat obsah báze v níž se vyskytuje, je záznam v souhrnném seznamu rozšířen symbolickou předponou dvou otazníků "??" a do třetího řádku záznamu pod řádek s popisem je doplněna otázka, kterou daný pojem umožňuje bázi zodpovídat.
- [ ] [Ttyp::DODĚLAT] [treq::31] - ukázka formátu tabulky #p/bp/metodika/báze/výstupy

##### interpretace
Výsledky interpretace, uvedené na začátku praktické části, jsou prezentovány dílčími pohledy na jednotlivé základní třídy a provedeným metodikou k nim asociovaných tříd. To znamená konkrétně 4 části, která každá z nich adresuje a argumentuje kroky provedené pro vytvoření prezentovaného modelu takovým způsobem, aby struktura textu těmto krokům odpovídala tak, že poskytne odpovědi na následující otázky:
- Proč byly konkrétní třídy přiřazeny k dané základní třídě?
- Proč je mezi třídami v dílčím pohledu taková struktura jaká je?
- Proč byly konkrétní třídy asociovány k základní třídě takovým způsobem jak jsou? 

Na závěr je uveden pohled na celý diagram, nicméně nezobrazuje nic, co by v dílčích pohledech již nebylo, proto tím i končí poslední analytický krok celé práce.

## Metodika tvorby DB schematu
- [ ] [Ttyp::UDĚLAT] ||: #p/bp/metodika/sw - Napsat účel postupu tvorby DB schematu | #p/bp/core
	- [ ] [testm::25min]|[HHTD::3]|[%targ::0]|[wtarg::69]účel 
	- [ ] [testm::15min]|[HHTD::2]|[%targ::0]|[wtarg::40]obecný postup 
	- [ ] [testm::45min]|[HHTD::4]|[%targ::0]|[wtarg::55]konkrétní postup 

#### Účel postupu

**Dílčí cíl:** Navrhnout schema pro databázi.

#### Obecný postup

### Konkrétní postup

#### Výstupy


## Metodika ověření výsledků

#### Účel postupu

**Dílčí cíl:** Ověřit úspěšnost dosažení výsledků

#### Obecný postup

### Konkrétní postup

#### Výstupy

