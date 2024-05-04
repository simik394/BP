
# Nápady
Schema v neo4j se od RDBs liší tím, že neomezuje tak pevně uloženou strukturou, naopak nabízí funkce pro refaktorování uložené struktury dat, automaticky v základním nástroji, podobně jako v případě webového GUI.
# plán
1. dokončit konceptuální model
2. určit nejlepší praktiky pro modelování dat ve vybrané databázi
3. vyhodnotit (a ZAZNAMENAT!) pro sestavený konceptuální model, které z nejlepších praktik jsou relevantní v jeho případě
   (představení nejlepších praktik - po jednotlivých částech grafu(node,rel,prop,lable) -> Která z uvedených doporučení aplikovat na jakou část modelu reprezentujícího, prací modelovanou doménu) [výsledky prezentovat v pořadí jednotlivých možných prvků grafové struktury] neboo ~~[výsledky prezentovat stejně jako v případě konceptuálního modelu]~~
   No imho by větší smysl dávala prezentace postupně podle průběhu tvorby, aby nikdo nemohl pochybovat a procesu vytváření. A prezentovat tak nejdříve 
   - které části byly transformovány jako "nodes" a jaké "lables" jsou použité
   - rels
   - které části byly transformovýny jako "properties"
4. * text do BP - Metodika návrhu DB schamatu
5. * text do BP - Metodika ověřování dosažení dílčích cílů



- * text do BP - prezentaceVýsledkůAnalýzy(sw)
- * text do BP - InterpretaceVýsledkůAnalýzyobsahu(báze)
- * struktura v textu BP reprezentující očištěný a předzpracovaný dataset pro následnou interpretaci


. definovat a popsat replikovatelný postup, kterým získám strukturu navrhované báze


# otázky
Ověření jako separátní dílčí cíl? je to ekvivalentní řešení k "rozprostření" jednotlivých metod pro ověřování mezi konkrétní části postupu, které ověřované prvky produkují?

---
Jak zpracovat pojmy získané z encyklopedie her, extrahoval jsem trochu větší počet než si vím rady s. Speciálně názvy kapitol jsou větší hromada, než umím zpracovat, mám tedy už v metodice říct, že je tedy vyhodnocovat nebudu a prostě je výsledků vyškrtat? 


dotaz
Je nějaký jiný způsob, jak dokázat validtu konceptuálního modelu?

Addressing Validity and Reliability
# komentáře
Celek znamená, že v práci musí být jasný záměr, postup, výsledek (jak to dopadlo) a též diskuse, z toho všeho činící otevřenou záležitost obecnějšího významu, a to v jednom textu - tedy myšlenky jasně vyřčené a vysvětlené, ne pouze naznačené, věty dokončené, texty na sebe v kapitolách navazující, úvodní a závěrečné shrnutí atd.
# Odevzdání
[Aplikovaná informatika (sharepoint.com)](https://vse.sharepoint.com/sites/intranet-studenti-FIS/SitePages/Aplikovan%C3%A1-informatika.aspx)

---


# TODO Podle Kapitol
> [!question]
> ```dataview
> TASK
> where contains(tags,"p/bp/úvod") or contains(tags,"p/bp/závěr")
> ```

## Metodika
```dataview
TASK
where contains(tags,"p/bp/metodika") and !fullyCompleted sort Cdist 
```
    
## Výzkum

```dataview
TASK
where contains(tags,"p/bp/teorie") and !fullyCompleted sort Cdist
```

## Vypracování
```dataview
TASK
where contains(tags,"p/bp/vypracování") and !fullyCompleted sort Cdist
```

## Diskuze
```dataview
TASK
where contains(tags,"p/bp/diskuze")
```



	
# _ %% fold %% 
> [!board]-
> [[Podklady/dashboard.bp.canvas|dashboard.bp]]


    ```dataview
	LIST file.tasks.text, any(file.tasks, (t) => t.tags)
	from [[BP/README|README]]
	WHERE any(file.tasks, (t) => !t.fullyCompleted)
	```

	```dataview
	table filter(file.tasks.text, (t) => t) as "Task Text"
	from #p/bp/metodika
	where file.tasks.text
	```
	
## ToDo \[\[BP/README]] - dataview %% fold %% 
⚗️🧼🚧💣
	```dataview
	TASK
	WHERE Ttyp = "DODĚLAT"
	```
	```dataview
	TASK
	WHERE Ttyp = "UDĚLAT"
	```
	```dataview
	TASK
	WHERE Ttyp = "VYLEPŠIT"
	```
	
	```dataview
	TASK
	WHERE Ttyp = "UČESAT"
	```
# Resources
## favs %% fold %%
[[Podklady/Odloženo/tmp.bp]]

[[Podklady/Pozorování/tábor23-artefakty.bp]]
[[bp.vedení]]
[[BP.Zadání


## Linked  

> [!NOTE]- n
> ```dataview
> table
> from #P/bp 
> ```

___
from: Linked-Zdroje-přehled on: 2024-04-08 19:04:15/