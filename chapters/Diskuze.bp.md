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

1. **Interpretace výsledků**: Začni s interpretací svých výsledků. Jak se tvé výsledky vztahují k tvým výzkumným otázkám nebo hypotézám? Byly tvé původní předpoklady potvrzeny nebo vyvráceny?
    
2. **Porovnání s existující literaturou**: Porovnej své výsledky s existujícími studiemi nebo literaturou. Souhlasí tvé zjištění s tím, co už bylo publikováno, nebo jsou nějaké rozdíly?
    
3. **Vysvětlení nečekaných výsledků**: Pokud jsi narazil(a) na nějaké nečekané výsledky, pokus se je vysvětlit. Můžeš navrhnout teorie, proč se tak stalo.
    
4. **Omezení studie**: Diskutuj o možných omezeních tvého výzkumu. Co mohlo ovlivnit tvé výsledky? Jak by omezení mohla ovlivnit interpretaci výsledků?
    
5. **Doporučení pro budoucí výzkum**: Na základě tvých zjištění a omezení, co by mohlo být téma pro budoucí výzkum? Jaké další kroky by mohly být podniknuty k dalšímu zkoumání tohoto tématu?
    
6. **Závěr**: Shrnutí hlavních bodů diskuze a jak tvé zjištění přispívají k oboru.
# Vysvětlení výsledků
## 1

"""
Pro případ, že by nebylo zřejmé jaké možnosti z toho vyplívají. Znamená to, že například lze napsat script, který se bude spouštět každých několik minut a při každém spuštění vybere soubory ze spicifkované lokace na disku, které byly od minulého spuštění upraveny. Pak získá pro každý z nich jeho obsah a vybere z něj konkrétní specifikované části (npř. nadpisy lvl.1, nadpisy lvl.2, záhlaví, url adresa souboru, etc.), kteréžto hodnoty následně uloží předepsaným způsobem třeba do gSheet tabulek. Výsledkem by tak byla průběžně aktualizované tabulka, představující index obsahu souborů v dané složce, umožňující v nich uložený obsah filtrovat. Což by, vzhledem k rozsahu činností, které spreadsheetové procesory podporují, nabídlo funkcionalitu pravděpodobně více než dostatečnou.

Ač využití gSheets jako hlavní rozhraní k prohledávaní báze sice byl původní záměr, bylo od něj v průběhu práce upuštěno a byla upřednostněna varianta plnohodnotné databáze. 
Je tomu primárně z toho důvodu, že v každém případě je stejně nezbytné implementovat kód, který by četl obsah daných souboru, rozlišoval v něm specifikované části a hodnoty zapsané v těchto částech by ukládal předepsaným způsobem do jiného softwaru s lepší podporou prohledávání uloženého obsahu. Tudíž je, tak jako tak, potřeba věnovat přinejmenším čas tomu tuto implementaci zrealizovat, což v rámci dobrovolnické organizace, kde nikdo nedostane za svůj čas ani korunu, může být obtížné. O to více v případě, kdy by za tolik úsilí byla pouze "excelová tabulka", která navíc nemusí ani být jednodušší na realizaci, využití nebo obojí, než obdobná komunikace s databází, jelikož ta má celý jazyk dedikovaný speciálně pro interakci s uloženými strukturami. Tudíž je možné předpokládat, že takovýto jazyk bude umožňovat šikovnější zapsání některých složitějších dotazů jednodušeji, než by byl byl zapsán dotaz odpovídající stejné výsledky skrze API, jehož primárním účelem je umožnit programový přístup, nikoliv "dokonalé" prohledávání.

V souhrnu tedy implementace integrace gDocs a gSheets nebude vyžadovat napsání podstatně odlišného objemu kódu, než integrace gDocs s databází, zatímco gSheets mají oproti databázím znatelně méně možností využití.
Bylo proto rozhodnuto pro využití databáze, jakožto nástroje, který byl pro účel uložení a prohledávání dat vyvinut, díky čemuž nebude jako ApsScripts a gSheets vyžadovat, aby všechny netriviální operace s daty byly definovány uživatelem, ale naopak v základu zahrnuje řadu funkcí, kterými může své využití usnadnit a zpříjemnit.

Znamená to avšak rovněž to, že navržený systém (podle předpokladu) nebude splňovat podmínku na ušetřený čas, pokud nebude dostatečně implementována automatická synchronizace uloženého obsahu mezi rozhraními a bude se synchronizace (aktualizování)  muset provádět manuálně. Řešením by bylo pouze provádět aktualizaci obsahu v delších časových rozmezích, jako třeba jednou za čtvrt roku. To by umožnilo provést některé kroky najednou pro více položek, místo pro každou zvlášť, čímž je možné dosáhnout razantního snížení času potřebného na údržbu. 
Variantay, kdy by nebylo nutné provádět tuto synchronizaci by byly v případě využití pouze jednoho nástroje. Což by byly buť samotné dokumenty (aktuální, nedostatečná varianta) a nebo samotná DB. Ta by však rovněž nebyla přijatelným řešením (z důvodu příliš vysokých nároků na běžného uživatele, aby mohl zaznamenat údaje), nicméně v roli pouze rozšíření a vylepšení aktuálního systému se její šance na přijetí cílovými uživateli znatelně zvyšuje [zdroj?].  


## 2

> [! nečekané]
> - chystamprogram v šabloně pro nové programy umožňuje zapisovat dobu trvání daného programu, nikoliv však podle této hodnoty vyhledávat a filtrovat

## 3

# Zhodnocení dosažení dílčích cílů

# Limitace

# Implikace pro další práci




Abstrakt
Tato práce softwarové řešení pro skautský oddíl které by umožnilo ukládání zápisů o připravených programech prostřednictvím alespoň stejně uživatelsky nenáročného rozhraní  pro zapisování jako mají dokumenty Google, které by navíc umožnilo i filtrování uloženého obsahu pomocí definovatelný parametrů. Proto porovnává čtyři běžné softwarové nástroje pro, aby z nich byla vybrána kombinace nástrojů, které by podle stanovených kritérií byla nejlepší. A tím tak určuje infrastrukturu která bude použita pro návrh. Tahle práce analyzuje tři existující báze skautských znalostí, vybírá z nich pojmy asociované se záznamy v dané bázi a na závěr analýzy interpretuje pomocí diagramu tříd podle UML. S vybranou infrastrukturou i určeným obsahem k zaznamenávání, identifikuje poslední krok nejlepší postupy pro modelování grafových dat na základě oficiálních publikací k vybrané databázi, jejichž pomocí nakonec transformuje diagram tříd na schéma vhodné uložení do vybrané databáze. Správnost výběru infrastruktury a míra její realizace je vyhodnocena pomocí implementace klíčových částí návrhu, které jsou identifikovány ve vztahu k možnosti dosažení konkrétních požadavků, které na systém práce specifikuje.