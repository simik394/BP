 
# Zv6
Měl by tak ==usnadnit přípravu kvalitních programů==.
## zaměření
### Oblast + podoblast: 
Organizace znalostí skautských programů + Software pro uložení znalostí
### Problém: 
  > Nalezení informací o připravených programech je v důsledku nesystematického, či chybějícího zápisu, přinejlepším poměrně časově náročné.

_(chybějící zápis)_ -Proč není zapsaný? -> 
Protože lidé nevidí dostatečný smysl v zápisu možných informací. -Proč?-> 
Protože se jim buď zatím nepodařilo najít přijatelný způsob využití, nebo pro vytvořené záznamy prostě žádný důvod nevidí. -Proč-> 
Protože *aktuálně neexistuje žádný systém, který by říkal co, jak a kam zapisovat. A zároveň naoplátku umožňoval v minimálním čase zobrazovat pouze specifické informace ani z malého, natož většího objemu záznamů*.
### Aspekt problému:
  Aktuálně **nemáme systém**, který by umožňil zároveň **snadné prohledávání i zápis**, ani samotné prohledávání sdílených znalostí.
### Cíl:
  Navrhnout systém pro sdílení *znalostí o připravených programech*. 


  Který by *uživatelům* poskytl možnost 
  **efektivního** (*rychle, správně*) 
  a zároveň 
  **příjemného** (*S co nejnižší bariérou, která je potřeba překonat pro použití novými uživateli.*) 
  vyhledávání v uloženém obsahu. 
  
  Spolu se zachováním 
  alespoň **stejné úrovně kvality uživatelské zkušenosti** 
  při zapisování, jako v aktuálním řešení. 


  Bez toho, aniž by navržený systém vyžadoval *více zdrojů na provoz* a *údržbu*, než sám ušetří při svém *využívání*.
 
### Dílčí cíle + metody:

| Analyzovat sw kandidáty na funkci uložiště v navrhované bázi (výběr sw). | analýza literatury [ ]                                                |
| ------------------------------------------------------------------------ | --------------------------------------------------------------------- |
| Analyzovat doménu skautských programů podle exestujících bází.           | analýza literatury [ ] konceptuální modelování :UML-classDiagram [ ]  |
| Navrhnout schema pro databázi.                                           | Z modelu pojmů podle doporučených postupů, na základě využití báze [] |
| Ověřit úspěšnost dosažení výsledků. <br>                                 | experiment/implementac []                                             |
## V systému  %% fold %%
### Název práce:
Návrh báze znalostí skautských programů
### Jazyková varianta:
Čeština 
### Rámcový obsah:
1. Prozkoumání východisek:
	- konceptuální modelování
	- metodiky řízení projektů
	- věcná problematika her a edukačních programů
2. Přínosy práce:
	- konceptuální model problematiky her a edukačních programů
	- návrh struktury báze znalostí
	- návrh systému procesů vývoje báze znalostí
 	 
### Rozsah práce:	
přiměřený obsahu 
### Literatura:
ŘEPA, Václav. Procesně řízená organizace. Praha: Grada Publishing, 2012. ISBN 978-80-247-4128-4.
 	 
Datum zadání:	únor 2024 	 
Datum odevzdání:	květen 2024

## pokus o cíle na začátku práce 
### Hlavní cíl varianty: %% fold %%
#### a
- Navrhnout zdarma provozovatelný cloud systém pro automatické indexování záznamů o připravovaných skautských programech v dokumentech google, umožňující *efektivnější* prohledávání jejich obsahu všem členům oddílu. 
 
 (na základě parametrů relevantních pro řízení přípravy a kvality výstupu.)
#### b
-  Navrhnout zdarma provozovatelný cloud systém pro automatické indexování záznamů o připravovaných skautských programech v dokumentech google, umožňující jejich *efektivnější* prohledávání na základě parametrů relevantních pro řízení přípravy a kvality výstupu obsahu všem členům oddílu. 

#### c
- Navrhnout zdarma provozovatelný cloud systém pro automatické indexování záznamů o připravovaných skautských programech v dokumentech google na základě parametrů relevantních pro , kvality výstupu  umožňující *efektivnější* prohledávání jejich obsahu všem členům oddílu. (.)
- 

usnadnit hledání inspirace, řízení přípravy i kvality výstupu.

usnadnit hledání inspirace při přípravě a zároveň kontroly kvality připraveného obsahu
### Dílčí cíle varianty: %% fold %%
- jak zapisovat údaje do dokumentů google
- návrh datové struktury
- výběr parametrů k zaznamenávání
- automatizace zrcadlení parametrů obsažených v dokumentech google do databáze
- automatizovat tvorbu indexu podle vybvraných parametrů
- umožnit prohledávání všem vedoucím
- dokumentovat vyžadované způsoby zápisu údajů
- umožnit prohledávání pro inspiraci pří přípravě
- umožnit prohledávání pro kontrolu pokroku při přípravě

### Dotaz: %% fold %%
Dobrý den pane profesore,
mám za to, že bych pro začátek svojí práce, než začnu modelovat, měl stanovit hlavní cíl a odpovídající dílčí cíle.

Podle doporučení, které jsem obdržel od pana doktora Sládka, hlavní cíl "v sobě shrnuje důvod, proč je práce vytvářená. Měl by být formulovaný tak, aby z něj bylo jednoduše pochopitelné, co je výstupem práce. Hlavní cíl práce by měl být orientovaný na řešení konkrétního problému."

Hádám proto, že ho potřebuji definovat konkrétněji než například "návrh systému pro vývoj báze znalostí skautských programů".
Myslím, že požadavkům by více odpovídala tato formulace:
"Navrhnout zdarma provozovatelný cloud systém pro automatické indexování záznamů o připravovaných skautských programech v dokumentech google na základě parametrů relevantních pro usnadnění hledání inspirace při přípravě a zároveň kontroly kvality připraveného obsahu, umožňující *efektivnější* prohledávání jejich obsahu všem členům oddílu."

Co se dílčích cílů týče, doporučení je "definovat je jako dílčí problémy, jejichž vyřešení je nutné pro naplnění hlavního cíle práce. Každý vedlejší cíl práce by měl mít jasnou vazbu na hlavní cíl práce. Z formulace vedlejšího cíle by měl být pochopitelný způsob, jak splnění tohoto vedlejšího přispívá k naplnění hlavního cíle práce".

Podle toho bych možná zvolil takovéto dílčí cíle:
určit obsah k zaznamenávání
automatizovat indexování
umožnit prohledávání
popsat využití systému

Nicméně mám značné pochybnosti ohledně svých formulací. U hlavního cíle primárně kvůli jeho délce a jisté krkolomnosti. Navíc přemýšlím, zda bych neměl blíže definovat efektivitu prohledávání.

Mohl byste mi prosím Vás poskytnout komentář ke vhodnosti mých formulací? 

Děkuji za Váš čas.
Šimon Trousil
### Komentář: %% fold %%
Dobrý den,
znamená to, že se chete přesunout k dr.Sládkovi? To bych musel udělat já. Dejte vědět.

Každopádně:

- Ta jeho definice cíle je poměrně přesná, jen bych ji tak nevázal na výstup práce. To jsou různé věci a měly by se rozlišovat. Výstup by měl být definován samostatně, nehledě na to, že jich může být víc (a asi i bude).

- Vaše formulace je celkem dobrá, ale až moc a zbytečně konkrétní. Proč například ausgerechnet gůgl? To můžete uvést uvnitř jako výsledek implementačního zamyšlení, což by bylo užitečné, neb Vás to přiměje k zamyšlení nad důvody (pokud to tam totiž uvedete, budete to muset důvodnit) a to je vždy ku prospěchu věci, soudím, že jste nic takového doposud neudělal, rozhodl jste se čistě intuitivně. Ale co je nejzávažnější - zdá se, že jste minul důvod, dle mého nejdůležitější - a to je ta báze znalostí (využít zkušenosti z programů k obohacení celé komunity). Tohle pořád vypadá jen na nějakou lokální evidenci a to mi připadne málo. Pravda, neminul jste to úplně, ale spíš to jen tak lehce naznačujete - mělo by to zaznít naplno a jasně.

- Ty dílčí cíle ještě poformulujeme. Nemusí to ale být hned. Je důležité, abyste pracoval systematicky a ty cíle si rámcově uvědomoval. Jejich přesná formulace je už spíš pro čtenáře, než pro operativní použití.

Pokud nechcete přejít k p.Sládkovi, pak první, co po Vás budu chtít, je začít pracovat na tom konceptuálním modelu (což předpokládá proniknutí do metody, resp. oživení této znalosti z předmětu Databáze). To je klíč k dalším akcím. A uvidíte na tom, že sdílení znalostí vyžaduje víc, než jen prostou evidenci. Udělejte prosím první návrh a přijďte si to po mejlové domluvě probrat.

Dejte prosím vědět, zda u mne zůstáváte a pokud ano, těším se a Vaši další návštěvu.

S pozdravy
V.Řepa
# v5   
## motivace %% fold %%
Co se tématu týče, původně mě zaujal task management jakožto klíčová podoblast projektového managementu, na které ve značné míře závisí jak efektivně (snadno/kvalitně) je možné dokončit produkt.
Nemám však vyloženě zájem v hledání nějaké optimální metody řízení. Jelikož produkt který mě zajímá, jsou skautské tábory, které každý rok pořádáme. 

Vzhledem ke skutečnosti, že každý kdo se na přípravě podílí, dělá tuto činnost dobrovolně. Typicky mají lidé motivaci připravovat, vymýšlet a provádět konkrétní programy s dětmi. Nicméně motivace pro koordinaci, delegování, či zaznamenávání průběhu, nebo finálního výsledku obohaceného o zpětnou vazbu, bývá značně nižší. 

Jako primární nedostatek tohoto stavu vnímam výsledné častno nekompletní záznamy o vytvořených programech, které umožňují jen velmi obtížné využití jako reference při plánování v dalších letech. Tudíž spousta práce se každý rok dělá od nuly, ačkoliv kdyby jsme měli standartizovaně sdílené zkušenosti z dřívějška, bylo by pravděpodobně možné dosáhnout výsledků mnohem snáze a navíc se vyhnout opakování stejných chyb. 

Avšak, nechci se asi zaměřovat čistě na sdílení znalostí. Rád bych, kromě základního sjednocení postupů pro záznam informací o plněných úkolech, sestavil semi-auto systém v prostředí Google Workspace (aktuálně využívané prostředí), který by umožnil 
manuálně zaznamenávat:
- úkoly k dokončení
- závislosti mezi úkoly
- stav a výstupy plněných úkolů

automaticky:
- agregovat zaznamenané údaje do reportů o průběžném pokroku
- doporučovat časový plán pro zaznamenané úkoly s ohledem na jejich závislosti
- doporučovat kterým vedoucím delegovat konkrétní úkoly v závislosti na jejich vytíženosti, osobních preferencích a dřívějších výsledcích

Výsledek by tak měl odstranit potřebu manuálně prohledávat jednotlivé dokumenty, nebo alespoň zásadně usnadnit správu záznamů a poskytovat aktualizované přehledy. Tím způsobem by jsme měli výhody vyplývající ze zaznamenaných údajů, a navíc by jsme zůstali ušetřeni většiny práce vyplývající z organizování řečených údajů.

## >> %% fold %%
manuálně zaznamenávat:
- úkoly k dokončení
- závislosti mezi úkoly
- stav a výstupy plněných úkolů

automaticky:
- agregovat zaznamenané údaje do reportů o průběžném pokroku
- doporučovat časový plán pro zaznamenané úkoly s ohledem na jejich závislosti
- doporučovat kterým vedoucím delegovat konkrétní úkoly v závislosti na jejich vytíženosti, osobních preferencích a dřívějších výsledcích
### filtrovat podle
- typ programu
- multi-dimonzionální hodnocení = kvality
- potřeby
	- trvání
	- vedoucí
	- materiál
	- prostředí
- 
- čas na úklid

# v4.1  %% fold %%
## téma BP

## cíle BP
> Sestavit systém pro řízení přípravy skautských táborů, který...
- 

___
from: BP.zaměření.v4 on: 2024-01-12 00:01:84


# v4 %% fold %%
## téma BP 
semi-automatický systém řízení práce vyžadované skautským táborem
v prostředí Google Workspace 05:26:57

___
from: 2023-12-16 04-57-30 on: 2023-12-16 05:12:51

# v3 %% fold %%

## Funkcionalita
---
[[Podklady/Nápady/Požadavky-katalog.bp]]


## Obsah %% fold %%
### Subject area:
- Task management

> [!question] Jakými větami začít? Uvést téma?
- [[TaskManagement|TM]] je všude, 

>[!question1] Co je TM? 
- životní cyklus úkolu

> [!question] Co si pod tím představit?
- v podnikovém prostředí je na [[TaskManagement|TM]] pohlíženo jako na komponentou [[ProjectManagement|PM]]. 

### Sub-area:
- Skaut a podniky mají [[skaut-podniky-rozdily-pro-TM|pár z hlediska TM klíčových rozdílů]]. 

> [!question1] Co zásadního z toho vyplývá pro [[TaskManagement]]? 
- minimalistický přístup k řízení


![[jorymackayWhatTaskManagement#^K77X3YANaUC6U85H2p3]]
- [[vytváření úkolů]] 
Jj. Protože vyřešit systematické zaznamenávání, šikovně využitelných údajů o naší práci by každopádně byl dobrý začátek.
- [[organizování úkolů]]  
Nvm, myslím že dokumentace, dělení úkolů na drobnější, by samo o sobě nebylo zase tak přínosné vzhledem k ostatním možnostem.
- [[prioritizace úkolů]] 
Nn


![[jorymackayWhatTaskManagement#^ZU7IFMPEaUC6U85H2p3]]

- [[plánování úkolů]]
Jj. Protože každý si program pro svoji družinu připravuje sám. Maximálně ve dvojici, ikdyž je tato možnost k dispozici, obvykle zůstává nevyužita. Podpora činnosti systémem by proto byla jen na místě.

- [[kolaborace na plnění úkolů]]
Nn


![[jorymackayWhatTaskManagement#^KWJS52C3aUC6U85H2p3]]
- [[plnění úkolů]]
Jj. Tady částečný překryv s plánováním úkolů.
Plnění dlouhodobých cílů jako "Vést družinu" bych nejspíše mohl vcelku jednoduše podpořit zefektivněním plánování krátkodobého, které si praktick každý vedoucí dělá sám pro sebe.

- [[kontrola plnění]] 
Nn

![[jorymackayWhatTaskManagement#^SWWUYA8QaUC6U85H2p3]]
-  [[optimalizace hodnototvorných procesů]]
Jj. Protože umožněním efektivnějšího zlepšování, bych pomohl zároveň i se všemi ostatními próblémy.


> [!question] Do kterých z těchto problematik se nechci pouštět?
- [[prioritizace úkolů]] 
Nn. Protože se nechci v rámci svého zaměření dostat k nutnosti zodpovídat otázky týkající se měření přínosnosti konkrétních úkolů vzhledem k nějakým jednotně stanoveným hodnotám.
Podobně jako u kontroly, bych se raději vyhnul potřebě řešit kvalitu výstupů.


- [[kolaborace na plnění úkolů]] 
Nn. Protože nechci ostatním zadávat práci. Navíc schůzky a výpravy jsou, například v porovnání s táborem relativně nenáročné na přípravu. Proto mi dává větší smysl, věnovat se raději podpoře činnosti jednotlivců, než se snažit prosadit zapojení více vedoucích do přípravy i jednodušších akcí.


- [[kontrola plnění]] 
Nvm. Sice se nechci věnovat problematice vyhodnocování kvality. Nicméně záznamenávání alespoň průběhu naplánovaných programů nebo využitelné zpětné vazby by bylo 

### Problem:
#### A
> [!error] nedostatečně efektvní/účelné využití dostupných dobrovolných lidských zdrojů

#### B
> [!error] nedostatečně efektvní/účelné využití dostupných sw nástrojů

#### C
> [!error] nedostatečné sdílení zkušeností z připravených programů

#### D
> [!error] jakékoliv řízení je práce "navíc" odlišná od vedení, které představuje primární motivaci pro byť jen přítomnost dobrovolných vedoucích
> = Nedostatečná motivace pro řídící činnosti

-  vybraný:
	- argumenty:

### Aspect of problem:

> [!question1] Jaký by byl nejvýznamnější společný nedostatek v těchto podoblastech, který mohu/chci zkusit vyřešit?

| n.| [[vytváření úkolů]] | [[organizování úkolů]] | [[plnění úkolů]] | [[plánování úkolů]] |
|----|----|----|----|----|
|Co by (pravděpodobně) pomohlo?|definované postupy pro zápis a využití záznamů o plněných úkolech|časová náročnost řídících procesů, převažuje mezi vedoucími k tomu dostupnou motivaci.   |podporující systém-maximalizace produktivity jednotlivců (automatizace? funkcionalita? náročnost provozu a implementace? |vhodně strukturované záznamy o dříve vykonaných úkolech umožňující data-based rozhodování|
|Co je (pravděpodobně) překážkou?|nesjednocené postupy > freestyle|krátkodobé plánování je typicky prováděno jednotlivci s minimální systematickou podporou |plnění krátkodobých úkolů je typicky prováděno jednotlivci s minimální systematickou podporou|nesjednocené postupy > freestyle|

> [!question] Kterou z příčin nejzásadnějšího problému se pokusím vyřešit?
-  vybraný aspekt: 
	- argumenty: 

### Aim:
> [!question1] Čeho chci v rámci řešení zvoleného problému dosáhnout?
#### 3.0
>[!aim] Vybrat a zdokumentovat doporučené postupy pro sdílení a využívání zaznamenaných údajů o připravených programech.

Komentář:

Předpokládám že nedostatečně informatické přinejmenším.

#### v3.1
>[!aim]  Vytvořit systém pro sdílení zkušeností z připravených programů.

Komentář:

Připadá mi jako nejzajímavější/nejpříjemnější varianta, ale nepřekvapilo by mě kdyby byla příliš obecná.
#### v3.2
>[!aim] Automatizovat přeměnu záznamů o připravovaných programech na sdílené zkušenosti snadno využitelné při přípravách dalších programů.

>[!aim] Automatizovat zpracování údajů zaznamenaných o připravených programech na sdílené zkušenosti efektivně využitelné při dalším plánování.

Komentář:

Nekonkrétněji stanovený cíl, nicméně si nejsem jistý, zda si chci stanovovat automatizaci stěží existujícího systému jako primární cíl.

-  vybraný aim: 
	- argumenty: 

> [!gray] ## Objectives:
> 1. k
> 2. l
> 3. j'  ^c201ob







 
