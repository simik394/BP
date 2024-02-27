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



# konceptuální model
## v2.2
![[concept-schema-ke-konzultaci2.2.png]]
## v2.1
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

- [x] U hry přidat parametr cíl/cíle hráčů?
Nebo vedle mechanik jako entitu obsaženou v pravidlech?
- [ ] Aktivity by měly být reusable (očištěné od prvků specifických pro konkrétní události).

- [ ] Události jsou primární produkt. Jaké jsou procesy jejich přípravy a provedení?

Mechanika je npř cíl hráče, hraní po týmech, či po jednotlivcích.
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
## v1
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
hlavní cíl aktivity
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
~~Cíl aktivity~~
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


