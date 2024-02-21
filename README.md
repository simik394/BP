

# ToDo 
```dataview
TASK
FROM "BP" or [[BP/README]] and !"BP/README"
WHERE !fullyCompleted 
```

# motivace 
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

# >> 
manuálně zaznamenávat:
- úkoly k dokončení
- závislosti mezi úkoly
- stav a výstupy plněných úkolů

automaticky:
- agregovat zaznamenané údaje do reportů o průběžném pokroku
- doporučovat časový plán pro zaznamenané úkoly s ohledem na jejich závislosti
- doporučovat kterým vedoucím delegovat konkrétní úkoly v závislosti na jejich vytíženosti, osobních preferencích a dřívějších výsledcích
## filtrovat podle
- typ programu
- multi-dimonzionální hodnocení = kvality
- potřeby
	- trvání
	- vedoucí
	- materiál
	- prostředí
- 
- čas na úklid
# V systému  
## Název práce:
Návrh báze znalostí skautských programů
## Jazyková varianta:
Čeština 
## Rámcový obsah:
1. Prozkoumání východisek:
	- konceptuální modelování
	- metodiky řízení projektů
	- věcná problematika her a edukačních programů
2. Přínosy práce:
	- konceptuální model problematiky her a edukačních programů
	- návrh struktury báze znalostí
	- návrh systému procesů vývoje báze znalostí
 	 
## Rozsah práce:	
přiměřený obsahu 
## Literatura:
ŘEPA, Václav. Procesně řízená organizace. Praha: Grada Publishing, 2012. ISBN 978-80-247-4128-4.
 	 
Datum zadání:	únor 2024 	 
Datum odevzdání:	květen 2024



# koncepty(entitní množiny) 
~~Družina~~
~~Člen~~
~~Aktivita~~
Programový blok
~~Výprava~~
~~Schůzka~~
~~Tábor~~
~~Hra (zábavné)~~
~~Naučný~~
~~Z5v~~
~~Záznam/zápis Plánu~~
~~Záznam/zápis průběhu~~
Komentáře k provedení
~~Vedoucí~~
~~Cíl aktivity~~
~~Bod stezky~~
~~Bod odborky/vlčka~~
~~Herní mechanika~~
~~Potřeba/materiál~~
~~Prostředí~~

# favs 
[[bp.notes]]

[[tábor23.bp]]
[[bp.vedení]]
[[BP.Zadání]]

# bp.Files-and-Folders 
___
## BP.Podklady
[[BP.Podklady|link]]
> [!def]- kořenová stránka pro /base

## <u>./chapters</u>
>[!def]- vznikají spojením vybraných a seřazených info-střepů 
forma: <mark class="hltr-blue">souvislé bloky textu</mark>

> [!view]-
> ```dataview
> list
> from "BP/chapters"

---
## ./assets
> [!def]- diagramy a dalši vizualizace

> [!view]-
> ```dataview
> list
> from "BP/assets"

## <u>./Podklady</u>
>[!def]- **vznikají kombinací ze <mark style="background: #FF5582A6;">Zotero annotací</mark> a <mark style="background: #BBFABBA6;">mých propojení</mark>**
**forma:** střepy a odkazy na ty importované poskládané v logickém pořadí
**obsah:** Podklady = zaměření | dosažení

> [!view]-
> ```dataview
> list
> from "BP/Podklady" AND !"BP/Podklady/Komunikace" AND !"BP/Podklady/Inspirace"
> ```

### ./Podklady/Inspirace
> [!def]- ukázky příkladů a oficiální zadání

### ./Podklady/Komunikace 
> [!def]- příprava komunikace s vyučujícími






---
# Cíle 
## Hlavní cíl:
### a
- Navrhnout zdarma provozovatelný cloud systém pro automatické indexování záznamů o připravovaných skautských programech v dokumentech google, umožňující *efektivnější* prohledávání jejich obsahu všem členům oddílu. 
 
 (na základě parametrů relevantních pro řízení přípravy a kvality výstupu.)
### b
-  Navrhnout zdarma provozovatelný cloud systém pro automatické indexování záznamů o připravovaných skautských programech v dokumentech google, umožňující jejich *efektivnější* prohledávání na základě parametrů relevantních pro řízení přípravy a kvality výstupu obsahu všem členům oddílu. 

### c
- Navrhnout zdarma provozovatelný cloud systém pro automatické indexování záznamů o připravovaných skautských programech v dokumentech google na základě parametrů relevantních pro , kvality výstupu  umožňující *efektivnější* prohledávání jejich obsahu všem členům oddílu. (.)
- 

usnadnit hledání inspirace, řízení přípravy i kvality výstupu.

usnadnit hledání inspirace při přípravě a zároveň kontroly kvality připraveného obsahu
## Dílčí cíle:
- jak zapisovat údaje do dokumentů google
- návrh datové struktury
- výběr parametrů k zaznamenávání
- automatizace zrcadlení parametrů obsažených v dokumentech google do databáze
- automatizovat tvorbu indexu podle vybvraných parametrů
- umožnit prohledávání všem vedoucím
- dokumentovat vyžadované způsoby zápisu údajů
- umožnit prohledávání pro inspiraci pří přípravě
- umožnit prohledávání pro kontrolu pokroku při přípravě 
# old
## BP.Issues
> [!todo]- Github
><iframe src="https://github.com/users/simik394/projects/2/views/6" frameBorder="0" width="650" height="600"></iframe>




## bp.Metodika.pre-konzultace
 - [ ] aktuální stav
	- [x] identifikovat artefakty vytvořené v rámci loňského tábora
	- [ ] modely fungování minulých let
	- [ ] sestavit testovací data

- [ ] vybrat dlouhodobé cíle junáka k zaměření se na
	- [ ] strategie junáka
		- [x] stáhnout
		- [ ] vytěžit
		- [ ] napojit
	- [ ] skautská křižovatka

- [ ] vyvodit featury pro systém ze zdrojů:
	- [ ] FAQ + issues řešené ve skupinových konverzacích
		- [ ] které chaty
		- [ ] vypsat
		- [ ] vybrat relevantní pro BP 
	- [ ] čekatelky plánování
		- [ ] archivovat
		- [ ] vytěžit
		- [ ] napojit
	- [ ] skautská křižovatka
	- [ ] tm SaaS features
		- [ ] list
		- [ ] vytěžit
		- [ ] sjednotit
	- [ ] develop.games
	- [ ] TLOU document

- [ ] top
	- [ ] přidat parametry k featurám umožňující vybrat nejvhodnější
	- [ ] připravit testovatelné user stories

- [ ] navrhnout implementaci
	- [ ] Které části GWorkspace využít pro jednotlivé funkce?
	- [ ] implementovat
	- [ ] otestovat

- [ ] diskutovat

- [ ] TLOU document - crunching, system support allows bigger creation, not to avoid crunch