
# artefakty
- Výjezdní táborová rada
	- 
	- cíle tábora 22
	- cíle tábora 23

- Všechny tabulky
	-  ů


- Etapa/
	- hotové etapy 23/
	- questy+bodování 23


- Programy/
	- old/


- Jídlo/
	- jídelníčky

- tabulky/
	- koupele 
	- bodování
	- ranní sběr

- forms/
	- z5v
	- návštěvy
	- rozpočet

- Vize tábora 23

- z5v.txt


# cíle

# mermaid experiment




```mermaid
flowchart LR
Start --> Stop
subgraph one
a1-->a2
end
a2-->Start
A-->|text|B
B-->Start

```
```mermaid
sequenceDiagram
Alice->>John: Hello John, how are you?
John-->>Alice: Great!
Alice-)John: See you later!
```

```mermaid
gantt
    title A Gantt Diagram
    dateFormat  YYYY-MM-DD
    section Section
    A task           :a1, 2014-01-01, 30d
    Another task     :after a1  , 20d
    section Another
    Task in sec      :2014-01-12  , 12d
    another task      : 24d
```


```mermaid
stateDiagram-v2
    [*] --> Still
    Still --> [*]

    Still --> Moving
    Moving --> Still
    Moving --> Crash
    Crash --> [*]
```


```mermaid
quadrantChart
      title Reach and engagement of campaigns
      x-axis Low Reach --> High Reach
      y-axis Low Engagement --> High Engagement
      quadrant-1 We should expand
      quadrant-2 Need to promote
      quadrant-3 Re-evaluate
      quadrant-4 May be improved
      Campaign A: [0.3, 0.6]
      Campaign B: [0.45, 0.23]
      Campaign C: [0.57, 0.69]
      Campaign D: [0.78, 0.34]
      Campaign E: [0.40, 0.34]
      Campaign F: [0.35, 0.78]
```

```mermaid
    requirementDiagram

    requirement test_req {
    id: 1
    text: the test text.
    risk: high
    verifymethod: test
    }

    element test_entity {
    type: simulation
    }

    test_entity - satisfies -> test_req
```

