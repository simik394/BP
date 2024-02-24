
# Files-and-Folders 

> [!files]- .
> ```dataview
> list
> from "BP" and !"BP/assets" and !"BP/chapters" and !"BP/Podklady"

> [!files]- ./chapters
> vznikají spojením vybraných a seřazených info-střepů 
forma: <mark class="hltr-blue">souvislé bloky textu</mark>
> ```dataview
> list
> from "BP/chapters"

> [!files]- ./assets
> diagramy a dalši vizualizace
> ```dataview
> list
> from "BP/assets"

> [!files]- ./Podklady
> **vznikají kombinací ze <mark style="background: #FF5582A6;">Zotero annotací</mark> a <mark style="background: #BBFABBA6;">mých propojení</mark>**
**forma:** střepy a odkazy na ty importované poskládané v logickém pořadí
**obsah:** Podklady = zaměření | dosažení
> ```dataview
> list
> from "BP/Podklady" AND !"BP/Podklady/Hledání vedení" AND !"BP/Podklady/Inspirace" AND !"BP/Podklady/Zastaralé"
> ```

> [!files]- ./Podklady/Inspirace
> ukázky příkladů a oficiální zadání
> ```dataview
> list
> from "BP/Podklady/Inspirace"

> [!files]- ./Podklady/Hledání vedení
> příprava komunikace s vyučujícími
> ```dataview
> list
> from "BP/Podklady/Hledání vedení"

## favs %% fold %%
[[tmp.bp]]

[[tábor23.bp]]
[[bp.vedení]]
[[BP.Zadání


# ToDo 
```dataview
TASK
FROM [[BP/README]] and !"BP/README"
WHERE !fullyCompleted 
```



