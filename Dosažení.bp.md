[[BP/README|README]]


# procesní model %% fold %%
## v1
1. plánování událostí (které a kdy budou)\[1-2 / rok]
2. příprava konkrétních událostí
	1. schůzka
	2. výprava
	3. tábor
3. pořádání události
4. archivace, rafinování získaných informací (aktuálně neexistuje D)

klíčový proces:
  1+3

podpůrné proc:
  2+4




# případy využití %% fold %%
Případy užití:  

## zaznamenávání aktivit, které by pomohly ve sledování některých cílů
(aktivit, které by jsme někdy mohli realizovat)

Zaznamenávat nápady

## hledání inspirace pří přípravě 
(tvorba nového i využití již zaznamenaného)  
### otázky: 
- 
## hledání při improvizaci 
(když NÁHODOU bude potřeba)  
### otázky: 
- Které aktivity/programy sledují konkrétní cíle (e.g. aktuální události)?
- Které aktivity/programy zapadají do požadovaného symbolického rámce?
- Které aktivity/programy jsou proveditelné s aktuálně dostupným vybavením?(vyškrtat co nemám)
## obohacení výstupů o zjištění ze Z5V 
(podpora NEopakovaní chyb a kontinuálního zvyšování kvality)  
### otázky: 
- Jaké programy byly a jaké parametry měly?
- Které části nefungovaly?
- Které části byly úspěšné?
## automatické tvorba úkolů na základě událostí a ostatních nekompletních záznamů
### otázky: 
- Které záznamy by bylo vhodné doplnit?
- Jak vylepšit přípravu a poučit se z chyb, ale i úspěchů?

## automatická tvorba přehledů o napojení vykonaných programu na cíle
(usnandní vyhodnocování kvality vykonaných programů + implicitně usnadní plánování dalšího směru a obsahu aktivit)
### otázky: 
-



# kompetenční otázky

Hry které se osvědčily a delší dobu nebyly na programu
Hry které se ještě nehrály
Osvědčený naučný program napojený na bod stezky, který většina ze členů družiny nemají splněný


# definice pojmů

Schůzka může mít výstup různý záznam.
-
Aktivita během události (část programu) může produkovat různý záznam.

 (a) \[část programu]  (p) \[může vyžadovat] (různý záznam)

Cíl má metriku
dílAktivity -- aktivita



Ggghhsjd %% fold %%
 Fffh


Tvorba ontologie která by na základě reasoningu aktualizovala/doplňovala 

Využití ontologie jako auto-tagovacího systému?
owlgred. Je to stále validní konceptuání model?

Definice "zábavná" vs. "Naučná"?
Které diagramy bych si pro implementaci alespoň dema měl připravit?
Kompetenční otázky klíčové pro moje modelování?




hodnocení + z5v psát vždy pod výstup práce ke kterému náleží (Aktivita, Program, Událost)
# zdroje


# konceptuální model

## v3.1 - plantUML
[[classDiagram.plantUML.bp]]

## v3.0 - test %% fold %%


```mermaid
classDiagram
        Cíl činnosti <|-- Strategie
        Cíl činnosti <|-- Bod_stezky
        Cíl činnosti <|-- Oddílový_Cíl činnosti
        Strategie "ideál 0..n" -- "reálný Cíl činnosti 0..n" Oddílový_Cíl činnosti 
        Bod_stezky "prostředek 0..n" -- "ideál 0..n" Strategie
        Bod_stezky "ffff" -- "ggggg" Typ_úkolu

```

```plantuml
foo "x" - "d" bar
Cíl_činnosti <|-- Strategie
Cíl_činnosti <|-- úkol_stezky
Cíl_činnosti <|-- výchovný_cíl
Typ_úkolu "r" -- "k" úkol_stezky
Strategie "ideál | 0..*" -- "prostředek | 0..*" výchovný_cíl 
úkol_stezky "prostředek 0..*" -- "cíl 0..*" výchovný_cíl

Událost "1..*"-- "n" Programový_blok
skautská_činnost <|-- Událost
```



## v2.2 %% fold %%
![[concept-schema-ke-konzultaci2.2.png]]
### Komentář: 
proč šestiúhelníky?
vlastnost "obsazena"? (to mělo být "obsažena")
bylo by lepší mít pojmenová konce vztahů více odpovídající realitě
> Dopředělat do standartního UML diagramu tříd

:
- [ ] proměnné parametry každé aktivity?
## v2.1  %% fold %% 
![[concept-schema-ke-konzultaci2.1.png]]
## v2
### schema:

> [!NOTE]
> - [x] Událost má symbolicky rámec a z toho vyplývá scénka

- [ ] Událost může mít přihlášené lidi 

- [ ] Aktivita může mít různé verze (starší/novější), a je důležité zachytit, ke které verzi byla poskytnuta z5v.

- [ ] Aktivity mohou mít několik lehce odlišných verzí. 
Verze by se měly drobně lišit, ne však příliš. pak nová aktivita. 
Každá verze má nějaké vlastní parametry (doba nabíjení, počet stanovišť, počet týmů, běhaná vzdálenost, symbolický rámec, ...)
- [ ] V rámci programového bloku by mělo být zaznamenáno konkrétní nastavení parametrů zvoleného programu. 
- [ ] Nicméně i v rámci aktivity může být specifikováno výchozí/doporučené nastavení těchto parametrů.

- [x] U hry přidat parametr Cíl činnosti/Cíl činnostie hráčů?
Nebo vedle mechanik jako entitu obsaženou v pravidlech?
- [ ] Aktivity by měly být reusable (očištěné od prvků specifických pro konkrétní události).

- [ ] Události jsou primární produkt. Jaké jsou procesy jejich přípravy a provedení?

Mechanika je npř Cíl činnosti hráče, hraní po týmech, či po jednotlivcích.
Mechanika = hráč musí/může/nemůže
#= hráč chce

---
- [ ] Členové mohou mít splněné některé body ke splnění

- [ ] Programový blok vychází z konkrétní události, mohl by tedy mít parametr "věk účastníků"

Indpiruj se u návrhu db pro DnD

---
Aktivita překreslování obrázku podle slovního popisu je hra, nebo naučná? A co překreslováné obrázky, co pro aktivitu představují?
Chci vážně dělit aktivity na zábavné, naučné a potřebné? > ANO

---
Program =vybrané aktivity s konkrétními parametry. By měly mít ještě připravené otázky jejichž zodpovězení proběhne ve z5v.

![[concept-schema-ke-konzultaci2.png]]
## v1 %% fold %% 
### schema:
![[concept-schema-ke-konzultaci1.png]]
### Komentáře-schema:

#### všeobecné
![[Conceptschemakomentar1#^KD92LVAFaME3Q98H8p1]]


#### pojmenování vztahů (5)
![[Conceptschemakomentar1#^SQW8CNSYaME3Q98H8p1]]
![[Conceptschemakomentar1#^29AIIULZaME3Q98H8p1]]
![[Conceptschemakomentar1#^DQEBPJ73aME3Q98H8p1]]
![[Conceptschemakomentar1#^9226QHQ5aME3Q98H8p1]]
![[Conceptschemakomentar1#^NNAEKGATaME3Q98H8p1]]

#### vztahy (2)
![[Conceptschemakomentar1#^AHZI6TLZaME3Q98H8p1]]
![[Conceptschemakomentar1#^22E9IMW7aME3Q98H8p1]]

#### pojmenování entit (2)
![[Conceptschemakomentar1#^5EPBB4R8aME3Q98H8p1]]
![[Conceptschemakomentar1#^G8NGTBVUaME3Q98H8p1]]


#### entity (3)
![[Conceptschemakomentar1#^YRKPC5Y6aME3Q98H8p1]]
![[Conceptschemakomentar1#^ZFXBAICMaME3Q98H8p1]]
![[Conceptschemakomentar1#^EC9RGPU6aME3Q98H8p1]]

#### parametry 
doba stavby >> čas na přípravu
![[Conceptschemakomentar1#^PQAHBZW4aME3Q98H8p1]]

#### gen/spec
hlavní Cíl činnosti aktivity
![[Conceptschemakomentar1#^FIPPGZWWaME3Q98H8p1]]

#### barvy
![[Conceptschemakomentar1#^PPTYFIE6aME3Q98H8p1]]


### model:
![[odm-Logical230703.png]]
### Komentáře-model:


## koncepty(entitní množiny) %% fold %%
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
~~Cíl činnosti aktivity~~
~~Bod stezky~~
~~Bod odborky/vlčka~~
~~Herní mechanika~~
~~Potřeba/materiál~~
~~Prostředí~~


# v0 %% fold %%
[[bp.Příprava]]
## Methods:
1. 
## Deliverables
1. 
## Contributions:
1. 
## Limitations:
1. 
## Structure:
1.
## Time-plan:
- 


