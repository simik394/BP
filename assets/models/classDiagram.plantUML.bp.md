


```plantuml
'-------------------------
'----CLASS DEFINITIONS----
'-------------------------
class Zn as "Znalost"
class Zk as "Zkušenost" {
+ datum
}
class sk-cin as "skautská činnost"
class udal as "Událost"
class schu as "Schůzka"
class vypr as "Výprava"
class tabor as "Tábor"
class progr as "Programový blok"

class pop-prub as "Popis průběhu"
class z5v as "Zpětná vazba"
class nazor as "Názor"
class akt as "Aktivita"
class a-hra as "Zábavná"
class a-edu as "Naučná"
class a-sup as "Potřebná"
class dil-a as "Díl aktivity"
class mech as "Mechanika"
class teor as "Teoretický podklad"
class metod as "Metodika"
class ruz-z as "Různý záznam"
class cil-c as "Cíl činnosti"
class strat-c as "Strategie"
class vych-c as "Výchovný cíl"
class stez-c as "Úkol ve stezce"
class typ-u as "Typ úkolu"

class ukol as "Úkol"
class out-p as "Výstup práce"
class clen as "Člen"
class skup as "Skupina"

class symb-r as "Symbolický rámec"
class scenka as "Scénka"
class tema as "Tématický motiv"
class popReal as "Popis realizace"

class poz-akt as "Požadavek aktivity"
class mater as "Materiál"
class vybav as "Vybavení"
class prostr as "Prostředí"



'----------------
'----GEN/SPEC----
'----------------
"out-p" <|-- "Zk"
	"Zk" <|-- "z5v"
	"Zk" <|-- "pop-prub"
	"Zk" <|-- "nazor"
	
"out-p" <|---- "Zn"
	"Zn" <|-- "dil-a"
		"dil-a" <|-- "mech"  
		"dil-a" <|-- "teor"
		"dil-a" <|-- "metod"
		"dil-a" <|-- "ruz-z"
	"Zn" <|-- "symb-r"
	
"out-p" <|-- "sk-cin"
	"sk-cin" <|-- "udal"
		"udal" <|-- "schu"  
		"udal" <|-- "vypr" 
		"udal" <|-- "tabor"
	"sk-cin" <|-- "akt"
		"akt" <|-- "a-hra"
		"akt" <|-- "a-edu"
		"akt" <|-- "a-sup"
	"sk-cin" <|-- "progr"
	
"cil-c" <|-- "strat-c"
"cil-c" <|-- "stez-c"
"cil-c" <|-- "vych-c"

"symb-r" <|-- "scenka"
"symb-r" <|-- "tema"
"symb-r" <|-- "popReal"

"poz-akt" <|-- "mater"
"poz-akt" <|-- "vybav"
"poz-akt" <|-- "prostr"

'--------------------
'----ASSOCIATIONS----
'--------------------

"typ-u" "0..1" -- "*" "stez-c"
"strat-c" "ideál | 0..*" --- "prostředek | 0..*" "vych-c" 
"stez-c" "prostředek 0..*" --- "cíl 0..*" "vych-c"

"progr" "\nsoučást | *"---"celek | *" "udal"
"progr" "celek | *"---"součást | *" "akt"

"progr" "1"---"plán | *" "pop-prub"
"progr" "1"---"záznam \nprůběhu \n| *" "pop-prub"

"cil-c" "cíl | *"--"   prostředek | *" "sk-cin"
"ukol" "proces | *"--"produkt | *" "out-p"
"out-p" " \n\n\n výstupy | *"--"názory | *" "z5v" 

"out-p" "výstup | 1"--"hodnocení | *" "nazor"
"z5v" "celek | 1"---"součást | *" "nazor"

"skup" "autoři | 1..*"---"sdělení | *" "z5v"
"ukol" "zadání | *"--"zodpovédný | 0..1" "clen"
"clen" "\n*"---"1" "skup"
"clen" "autor | 0..1"--"popis | * \n" "pop-prub"
"akt" "*" -- "*" "poz-akt"
"ruz-z" "*"--"*" "akt"
"a-hra" "hra | *"--"pravidlo | *" "mech"
"a-edu" "*"--"*" "metod"
"a-edu" "*"--"*" "teor"


"symb-r" "*"--"*" "sk-cin"
```



znalosti by měly být reusable 
bloky by měly být konkrétní implementace
události veřejně v kalendáři
nicméně pak musím ke každému vést vztah zvlášť
když je ale sdružím pod skautskou činnost, mám problém s tím, že už pak nebudou pod znalostmi, které mají značit reusabilitu


"symb-r" "x"--"x" "akt"
"symb-r" "x"--"x" "progr"


"progr" -- "Zn"
class ArrayList as "AL" extends AbstractList
foo "x" - "d" bar

add díly symbolický rámec

add požadavky aktivity



s "prostředek 0..*" --- "prostředek 0..*" U
a "\n\n\nprostředek 0..*" --- "prostředek 0..*" b
a "prostředek 0..*" --- "prostředek 0..*" c
f "prostředek 0..*" --- "prostředek 0..*" h
a "prostředek 0..*" --- "prostředek 0..*" f
a "\n prostředek \n  0..*" -- " 0..*" skautská_činnost
f "prostředek 0..*" --- "prostředek 0..*" Strategie
U "prostředek 0..*" --- "prostředek 0..*" Událost
b -- c
fff -- bbb
a "prostředek 0..*" --- "prostředek 0..*" lll
f "prostředek 0..*" --- "prostředek 0..*" ll
a "prostředek 0..*" --- "prostředek 0..*" l
qqq "prostředek 0..*" --- "prostředek 0..*" c
qq "prostředek 0..*" --- "prostředek 0..*" h
q "prostředek 0..*" --- "prostředek 0..*" f



<< (D,orchid) >>
sk-cin <|-- Program

