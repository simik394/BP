---
up:
  - "[[../README|README]]"
---

Problém
 ![[BP/drafts/Zaměření.bp#Problém]]
Cíl
  ![[BP/drafts/Zaměření.bp#Cíl]]
##### Doporučený obsah
Discussion—What does it mean after all and so what?

results explained?
objectives achieved? 
limitations?
implications for future work?

#### Dotazy
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

# Určení úspěšnosti dosažení
## Výběr pojmů
## Minimalistická implementace

## Správnost konceptuálního modelu

## Ověření využitelnosti báze


# 