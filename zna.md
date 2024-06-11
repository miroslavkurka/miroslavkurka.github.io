# Object Intersection and Rice - Siff Algortihm for Formal concept analysis
Vsetko viac formalne a s dokazmi je v [ZNA textbook](https://unibook.upjs.sk/archiv/sk/informatika/1423-zaklady-znalostnych-systemov)

TDLR: Co treba vediet na pochopenie: 
 - co je to operator (https://en.wikipedia.org/wiki/Operator_(mathematics)) 
 - co je to uzaver mnozin 
 - co je to formalny kontext 
 - co je to derivacny operator
 - co je to uzaverovy operator
Ak toto vsetko viete, staci skocit na kapitolu [Object Intersection Algorithm](#object-intersection-algorithm)


## Co je to uzaver mnoziny?
Uzaver mnoziny je mnozina, ktora obsahuje vsetky prvky, ktore su vytvorene z povodnej mnoziny pomocou nejakeho operatora.
Stale plati ze pre mnozinu X a jej uzaver cl(X): X je podmnozina cl(X) a cl(cl(X)) = cl(X) footnote(tato vlasnost sa vola indepodencia, taktiez potrebne vediet pre derivacne operatory, galois connection, atd.) 
Preco je to pravda? Uvedme priklad mam X = {1, 2, 3} a operator "nasobenie", tak cl(X) = {1,2,3,4,6,9}. A to preto ze kazdy vysledok nasobenia a * b, kde a,b su z X musi byt v cl(X). To ze X je podmnozina cl(X) je zrejme.
Vseobecne mame nejaky operator H ktory vie generovat nove prvky z X a uzaverom tejto mnoziny bude skupina vsetkych tychto moznych generovanych prvkov.

## Co je to formalny kontext?

Formalny kontext je trojica (B, A, R), kde B je mnozina objektov, A je mnozina atributov a R je binarna relacia medzi B a A. Tato relacia hovori o tom, ktore atributy patria k danemu objektu.

## Co je to derivacny operatr? 


## Object Intersection Algorithm
Link na clanok [Object Intersection Algorithm](https://www.researchgate.net/publication/220853707_Object_Intersection_Algorithm)

## Rice - Siff Algortihm

Clanok o tomto algoritme vysiel v [Electronic Notes in Theoretical Computer Science 40 (2002)](https://www.sciencedirect.com/journal/electronic-notes-in-theoretical-computer-science) strana 24, bohužiaľ od roku 2021 je tento časopis zrušený.

Narozdiel od object intersection v tomto algoritme rozhodujeme ci pridame koncept do kontextu na zaklade pseudo metriky.
Ta je definovana ako: `\ro((X,Y),(X',Y'))= 1- |Y ∩ Y'|/|Y ∪ Y'|`, kde X, X' su objekty a Y, Y' su atributy. A usporiadana dvojica (X,Y) je koncept.

```
Procedure Rice-Siff Algorithm (G)
Input: A formal context G = (B,A,R) 

C:= 


```

V pythone vyzera implementacia nasledovne:
```python

def rice_siff_algorithm():
    pass


```


## Factorizaton of a matrix (Set Covering Problem)

### Bottleneck 