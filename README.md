
# otázky
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
> [!úvod + závěr]
> ```dataview
> TASK
> where contains(tags,"p/bp/úvod") or contains(tags,"p/bp/závěr")
> ```

## Metodika
```dataview
TASK
where contains(tags,"p/bp/metodika") sort Cdist
```
    
## teorie

```dataview
TASK
where contains(tags,"p/bp/teorie") sort Cdist
```

## Vypracování
```dataview
TASK
where contains(tags,"p/bp/vypracování") sort Cdist
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