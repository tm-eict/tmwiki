---
title: Untitled Page
description: 
published: true
date: 2021-06-10T13:00:15.601Z
tags: 
editor: markdown
dateCreated: 2021-06-10T13:00:09.047Z
---

---
title: Samenvatting Peter digitaal / Artistieke vrijheid van Dries
created: '2021-02-15T09:20:50.736Z'
modified: '2021-06-10T12:55:37.376Z'
---

# Samenvatting Peter digitaal / Artistieke vrijheid van Dries

## Formules
### Amdahl's law (slide 19)

#### speedup = $\frac{1}{(1-verbeterd deel) + (\frac{verbeterd deel}{verbeteringsfactor})}$
```
1 - verbeterd deel = niet verbeterd deel
verbeterd deel = deel dat versneld is
verbeteringsfactor = hoeveel sneller
```

vb: 
Versnelling van 1.6 op 80% van programma
speedup = $\frac{1}{0,2 + (\frac{0,8}{1,6})}$

> Het is beter om een groot deel een beetje te versnellen dan een klein deel heel veel


### Vergelijking processoren (slide 44)
(enkel stroom en snelheid)

#### X = Stroomverbruik<sub>A tov B</sub> $\times$ tijdsverhoudingtaak<sub>A tov B</sub>
X $\lt$ 1 = beter ; X $\gt$ 1 = slechter
vb:
A verbruikt 30% meer dan B,  A doet 50% minder lang over taak dan B
X = 1.3 $\times$ 0.5 = 0.65 $\to$ A is beter dan B

### Energie en Stroom in microprocessor (slide 45)
#### P = $\frac{1}{2}$ $\times$ C $\times$ $U^2$ $\times$ f $\times$ $\alpha$
(vast stroomverbruik)
P: Active power / Energie dynamisch
C: Capacitieve belasting
U: Spanning
f: (schakel)frequentie
$\alpha$: In verhouding tot maximale werking

#### $\frac{E_{nieuw}}{E_{oud}} = \frac{U * nieuwPercentage}{U^2}$
(variabel strrromverbruik)




### Kost IC
#### Cost<sub>IC</sub> = $\frac{Cost_{die} + Cost_{testing} + Cost_{packaging} + Cost_{deftest}}{Winst op def test}$
#### Cost<sub>die</sub> = $\frac{Cost_{wafer}}{(\frac{\#dies}{Wafer}) + winst_{die}}$
#### $\frac{\#dies}{wafer}$ = $\frac{Opp_{wafer}}{Opp_{die}}$ - $\frac{Omtrek_{wafer}}{\sqrt{2 \times Opp_{die}}}$ = $\frac{\pi \times (\frac{D_{wafer}}{2})^2}{Opp_{die}}$ - $\frac{\pi \times D_{wafer}}{\sqrt{2 \times Opp_{die}}}$
vb:
$D_{wafer}$ = 30cm
$Zijde_{die}$ = 1.5cm

$\#dies$ = $\frac{\pi \times (\frac{30cm}{2})^2}{2,25cm^2}$ - $\frac{\pi \times 30cm}{\sqrt{2 \times 2,25cm^2}}$ 
= 269.73 => 269 dies/wafer

### Dependability (slide 52)
Beschikbaarheid module = $\frac{MTTF}{MTTF+MTTR}$ (in uren)

MTTF = Mean time to failure

MTTR = Mean time to repair

failure rate = som($\frac{aantal componenten}{MTTF component}$)

vb: $\frac{10}{1.000.000} + \frac{1}{500.000} + \frac{1}{1.000.000} + \frac{1}{200.000} + \frac{1}{200.000} = \frac{23}{1.000.000} = 23FIT$

FIT = Failure in time

MTTF = $\frac{1}{failure in time}$

### Performance (slide 58)

#### $\frac{Execution time_{y}}{Execution time_{x}}$ = $\frac{Performance_{y}}{Performance_{x}}$ => Verhouding exec en performance time is gelijk

#### throughput = $\frac{1}{latency}$ = $CPU_{performance}$ = $\frac{1}{exec time}$ (in MIPS)

throughput: synoniemen = performance levels[MIPS] en bandbreedte [GB/s]
MIPS: Million instructions per second
Latency: Tijdsduur van programmaprocess (zonder I/O)
synoniemen: exec time, response time, cpu time

### Set associative cache, block adress set (slide 9 deel 2)
#### Block address in set  = Block adress % Aantal blocks in set
% = modulo / rest



















