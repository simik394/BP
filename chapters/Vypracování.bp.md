--- %% fold %% %% fold %%
aliases: 
up: %% fold %%
  - "[[../README|README]]"
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


# !!!Infrastruktura pro bázi 
**(Vyhodnocení výsledků analýzy (sw))**
## Předpoklad
Jak bylo stanoveno v metodice, tato část popisuje infrastrukturu (softwarové nástroje) do základu navrhované báze, která by v souladu s cílem práce (viz. Cíl), nevyžadovala víc prostředků na údržbu, než sama ušetří a zároveň přitom odpovídal  i ostatním požadavkům Cíle.

Konkrétně, vzhledem k tomu, že aktuálně není k dispozici způsob, jak změřit ušetřený čas při využívání báze, je vycházeno z předpokladu, že pokud budou vyžadovány lidské či finanční prostředky na to, aby byl obsah v gDocs udržován konzistentní s obsahem v efektivně prohledatelné databázi, nebude ušetřený čas větší, než ten vyžadovaný na údržbu. 

""" %% fold %%
 Proto bude popsána možnost automatizace synchronizačního procesu taková, která by nevyžadovala finanční prostředky na svůj provoz . 
 Pro 
 Rovněž budou definovány konkrétní funkcionality, na kterých závisí proveditelnost popsaného způsobu.

 Na základě vybraných kandidátů a jim dostupných možností bylo určeno
 todo %% fold %% 
  - [ ] f
## !!-Návrh infrastruktury
### !Rozhraní pro zapisování obsahu do báze
gDocs i gSheets - skvělé, user friendly, cloud native, free, SaaS, alreadyUsed

Nicméně efektivní prohledávání uloženého obsahu, natož pak prohledávání alespoň se blížící urovni možností nabízených databázemi, prostě gDocs nemají ve svém repertoáru nabízených služeb. Kdyby dovedly alespoň spolehlivě vyhledávat mezi více dokumenty i podle jejich obsahu a nejen podle názvu, času změny, autora a dalších explicitně uvedených informací, možná by se dalo vystačit i s jejich funkcemi. Bohužel to není ten případ.

Co však Google ve svém repertoáru má, je služba s názvem Apps Scripts. 

- obsah z gDocs je možné číst s pomocí AppsScripts?
- je možné s pomocí AppsScripts přistupovat pouze ke specifickým částem dokumentů na základě jejich absolutního i relativního umístnění ve struktuře dokumentu?
- je s pomocí AppsScripts možné komunikovat s Neo4j?


""" %% fold %%
 > gDocs + AppsScripts - (= s automatizovanou jednosměrnou synchronizací (zrcadlení) změn v dokumentech do DB)

   pozor na to, že apps scripts mají runtime limity, proto je potřeba dát si pozor, aby spouštěné scripty nebyly příliš časově náročné, protože pokud běži déle než 30(90?) vteřit, platforma je automaticky přeruší.

 Na základě vybraných kandidátů a jim dostupných možností bylo určeno
### !Rozhraní pro čtení obsahu z báze
samotná DB by asi nebyla přijatelným řešením, nicméně v roli pouze rozšíření a vylepšení aktuálního systému se její šance na přijetí cílovými uživateli znatelně zvyšuje [zdroj?].  Avšak ani zakomponování tohoto nástroje není zcela bezproblémové

""" %% fold %%
 > Neo4j - 
## !!Ověření realizovatelnosti navržené infrastruktury
### !Demo proces automatizované údržby konzistence uložených dat mezi rozhraními 


""" %% fold %%
 flowchart
### !Klíčové kousky kódu


""" %% fold %%

 celý kód na githubu (+video proof)
# !!!Model pojmů
## !Základní definice
model 
 ![[../assets/images/Pasted image 20240425140659.png]]

""" %% fold %%
 myšlenky %% fold %%
  -
 todo %% fold %%
   - [ ] [Ttyp::UDĚLAT]|[Cdist::3]|[HHTD::5] ||: #p/bp/vypracování/modelPojmů/základní REASONING pro základní definici
## !Rozšíření základních tříd
### !program

""" %% fold %%
 pojmy/baze %% fold %%
  - chystamprogram - Název, Anotace, Výchovný cíl, oblast rozvoje, podoblast rozvoje, napojení na stezku, obsah programu, přílohy, symbolický rámec, reflexe, zdroje, autor
  - sdílený disk - zpětná vazba
  - encyklopedie her - Název, Alternativní název
 todo %% fold %%
  - [ ] [Ttyp::UDĚLAT]|[Cdist::3]|[HHTD::4] ||: #p/bp/vypracování/modelPojmů/rozšířený/program model + reasoning
### !aktivita

""" %% fold %%
  pojmy/baze %% fold %%
   - chystamprogram - druh aktivity, doba trvání, doba na přípravu, velikost skupiny, věk skupiny, místo konání, psychická náročnost, fyzická náročnost, pomůcky a materiál, bezpečnost, metodické poznámky
   - encyklopedie her - 'věci, které jsou ke hře potřebné'(~pomůcky a materiál), počet hráčů(~velikost skupiny), místo(~místo konání), věková kategorie(~věk skupiny), věk nejmladšího; Věk nejstaršího, trvání({doba trvání})
  todo %% fold %%
   - [ ] [Ttyp::UDĚLAT]|[Cdist::3]|[HHTD::4]  ||: #p/bp/vypracování/modelPojmů/rozšířený/aktivita  model + reasoning
### !hra

""" %% fold %%
 pojmy/baze %% fold %%
  - encyklopedie her - průběh hry; úlohy hráčů; losování; rozpočitadla; herní území; jednolitý děj; zřetelné odlišených částí; formulky při hře užívané; tradiční dialogy; melodie v notách; nakreslený obrazec; jen chlapců, jen děvčat,; chlapci i děvčata; pokračující neomezenou dobu; určitém ročním období; dokumentární fotografie; charakteristické okamžiky; soutěživá; nesoutěživá; Role hráčů; hra, při které rozhodují o vítězství a porážce jen schopnosti hráčů; hra, ve které má jistou úlohu náhoda a štěstí; tělesné vlastnosti a schopnosti uplatňující se ve hře; Hrubá motorika (rychlost, síla, obratnost, vytrvalost); jemná motorika (zručnost, rovnováha, nervosvalová koordinace, orientacev rostoru, speciální dovednosti); duševní schopnosti uplatňující se ve hře; povahové vlastnosti projevující se ve hře; prvky, ze kterých je hra složena(Běh — skákání — zvedání a nošení — házení a vrhání — odrážení — chytání — zápasení — přetahování — taneční pohyby — zpěv — dialog — hraní rolí podobných divadlu — schovávání a hledání.)}
 todo %% fold %%
  - [ ] [Ttyp::UDĚLAT]|[Cdist::3]|[HHTD::5]  ||: #p/bp/vypracování/modelPojmů/rozšířený/hra model + reasoning
### !událost


""" %% fold %%
 sdílený disk - plánovaný průběh, skutečný průběh
 todo %% fold %%
   - [ ] [Ttyp::UDĚLAT]|[Cdist::4]|[HHTD::3]  ||:  #p/bp/vypracování/modelPojmů/rozšířený/událost model + reasoning

## !Posouzení vybrané výseče reality
### !Modely

""" %% fold %%
 myšlenky %% fold %%
  -
 todo %% fold %%
  -
### !Rozdíly

""" %% fold %%
 myšlenky %% fold %%
  -
 todo %% fold %%
  -
# !!Schema databáze
## !!!Návrh schématu
### !lables, nodes (transformed)

""" %% fold %%
 myšlenky %% fold %%
  -
 todo %% fold %%
  -

### !relationships (transformed)

""" %% fold %%
 myšlenky %% fold %%
  -
 todo %% fold %%
  -

### !properties (transformed)

""" %% fold %%
 myšlenky %% fold %%
  -
 todo %% fold %%
  -



## !!Ověření kompetencí navrženého schématu
### !Vzorová data %% fold %%


""" %% fold %%
 myšlenky %% fold %%
  -
 todo %% fold %%
  -
### !Vzorová queries 
odpovídající kompetencím existujících bází

""" %% fold %%
 myšlenky %% fold %%
  -
 todo %% fold %%
  -