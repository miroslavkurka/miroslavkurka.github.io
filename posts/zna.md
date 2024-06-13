# Object Intersection and Rice - Siff Algortihm for Formal concept analysis
Vsetko viac formalne a s dokazmi je v [ZNA textbook](https://unibook.upjs.sk/archiv/sk/informatika/1423-zaklady-znalostnych-systemov)

TDLR: Co treba vediet na pochopenie: 
 - co je to operator (https://en.wikipedia.org/wiki/Operator_(mathematics)) 
 - co je to uzaver mnozin 
 - co je to formalny kontext 
 - co je to formalny koncept 
 - co je to derivacny operator
 - co je to uzaverovy operator
Ak toto vsetko viete, staci skocit na kapitolu [Object Intersection Algorithm](#object-intersection-algorithm)


## Co je to uzaver mnoziny?
Uzaver mnoziny je mnozina, ktora obsahuje vsetky prvky, ktore su vytvorene z povodnej mnoziny pomocou nejakeho operatora.
Stale plati ze pre mnozinu X a jej uzaver cl(X): X je podmnozina cl(X) a cl(cl(X)) = cl(X) footnote(tato vlasnost sa vola indepodencia, taktiez potrebne vediet pre derivacne operatory, galois connection, atd.) 
Preco je to pravda? Uvedme priklad mam X = {1, 2, 3} a operator "nasobenie", tak cl(X) = {1,2,3,4,6,9}. A to preto ze kazdy vysledok nasobenia a * b, kde a,b su z X musi byt v cl(X). To ze X je podmnozina cl(X) je zrejme.
Vseobecne mame nejaky operator H ktory vie generovat nove prvky z X a uzaverom tejto mnoziny bude skupina vsetkych tychto moznych generovanych prvkov.


## Co je to uzaverovy operator?
Pred vysvetlenim potrebujeme definovat este uzaverovy system. Ten je neformalne len pre nejaku mnozinu G mam uzaverovy system S ked spravim cl(G) s tym ze ten operator na generovanie prvok bude prienik. Tj. priklad G={a,b} tak potom uzaverovy system moze byt S = {∅,{a,b}}, a to lebo plati ze prienik prvkov z S su sami v S. Nemusi to byt jediny uzaverovy system, pre nas priklad existuje aj uzaverovy system S = {∅, {a}, {b}, {a, b}}. Kde nas prvy uzaverovy system bol najmensi mozny a druhy je najvacsi mozny. Formalna definicia je:
```
Uzaverovym systemom na mnozine G nazyvame taku mnozinu jej podmnozın, ktora ako jeden z jej prvkov obsahuje celu mnozinu G a je uzavreta na prieniky.
```
*Uzaverovy operator* 
je to kazde zobrazenie na G, ktore splna tri podmienky:

1.) monotonnost X ⊆ Y ⇒ ϕX ⊆ ϕY

2.) extenzivnost X ⊆ ϕX (toto vypliva z uzaveru mnoziny cl(G), je to popisane v [hore](#co-je-to-uzaver-mnoziny) )

3.) idempotencia ϕϕX ⊆ ϕX (podobne ako v cl(G), presny dokaz je v skriptach)

## Co je to formalny kontext?

Formalny kontext je trojica (B, A, R), kde B je mnozina objektov, A je mnozina atributov a R je binarna relacia medzi B a A. Tato relacia hovori o tom, ktore atributy patria k danemu objektu.

## Co je to derivacny operator? 

Mam (B, A, R) formalny kontext. Potom pre vsetky X ⊆ B (obekty) a Y ⊆ A (atributy) definujem derivačné operátory takto:

$$ \uparrow X = {a \in A \mid \forall b \in X: (b, a) \in R} $$
Toto znamena, ze sipka hore X vrati vsetky take atributy ktore maju vsetky objekty v mnozine X. 

$$ \downarrow Y = {b \in B \mid \forall a \in Y: (b, a) \in R} $$
Toto znamena ze sipka dole Y vrati vsetky take objekty ktore maju vsetky spolocne atributy v mnozine Y.


Urobim si priklad:

*   **B (zvieratká):** {mačka, pes, vták}
*   **A (atribúty):** {má srsť, má krídla, vie lietať}
*   **R (relácia):**
    *   (mačka, má srsť) ∈ R
    *   (pes, má srsť) ∈ R
    *   (vták, má krídla) ∈ R
    *   (vták, vie lietať) ∈ R

Potom,
* ↑({mačka, pes}) = {má srsť}
* ↓({má srsť}) = {mačka, pes}


## Co je to formalny koncept?

Ak uz mam formalny kontext (B, A, R) a dve jeho derivacne operatory (↑, ↓) tak potom formalny koncept je kazda taka dvojica (X,Y) pre ktoru plati ↑ (X) = Y a ↓ (Y) = X. 

Ak spravim uzaver na cl(B, A, R) dostanem mnozinu vsetkych formalnych konceptov 

## Object Intersection Algorithm
Link na clanok [Object Intersection Algorithm](https://www.researchgate.net/publication/220853707_Object_Intersection_Algorithm)

Tento algoritmus vezme formalny kontext a pre kazdy objekt najde vsetky jeho atributy. Ako prvy concept sa vytvori 

V pseudo-pythone 

```python

def object_intersection(context):
    # TODO, lepsie napisat pseudokod 
    concepts=[[0:len(context[0])]] # 
    for row in BAR:
        for concept in concepts:
            intersection= intersect(row,concept) 
            if intersection not in concepts:
                concepts.append(intersection)
    return concepts

```


## Rice - Siff Algorithm 
Clanok o tomto algoritme vysiel v [Electronic Notes in Theoretical Computer Science 40 (2002)](https://www.sciencedirect.com/journal/electronic-notes-in-theoretical-computer-science) strana 24, bohužiaľ od roku 2021 je tento časopis zrušený.

Narozdiel od object intersection v tomto algoritme rozhodujeme ci pridame koncept do kontextu na zaklade pseudo metriky (tiez sa to da najst ako Jaccart distance).
Ta je definovana ako: `\ro((X,Y),(X',Y'))= 1- |Y ∩ Y'|/|Y ∪ Y'|`, kde X, X' su objekty a Y, Y' su atributy. A usporiadana dvojica (X,Y) je koncept.


V pseudo-pythone vyzera implementacia nasledovne:
```python

def rice_siff(context):
    # toto vyzera strasidelne, ale v podstate to vezme context a vrati pole s mnozinami kde kazdy prvok mnoziny je index na ktorom v contexte bola hodnota true 
    # tj pre [1, 0, 1] bude context [{0,2}]
    concepts = [(set([i]), set(j for j, x in enumerate(context[i]) if x == 1)) for i in range(len(context))] 

    while True:
        closest_pair = find_closest_pair(concepts) 
        (X1, Y1), (X2, Y2) = closest_pair
        if distance(Y1, Y2) > pseudometric_ro(X1, Y1, X2, Y2): 
            break
        new_extent = X1 | X2 
        new_intent = Y1 & Y2 
        concepts.remove((X1, Y1))
        concepts.remove((X2, Y2))
        concepts.append((new_extent, new_intent))

    return concepts 

```


## Factorizaton of a matrix (Set Covering Problem)

### Bottleneck 

Kedze faktorizacia konceptov je v podstate hladanie "obdliznika" v tabulke BAR, ktory zachytava co najviac konceptov. Mozme tento problem preformulovat ako set covering. Set Cover z predmetu APA alebo zo Zlozitosti vieme ze je NP-uplny problem. Teda neexistuje algoritmus, ktory by ho riesil v polynomialnom case. Moja greedy implemetacia je prevzata z wikipedie a je velmi pomala pri dostatocne velkych maticiach. 


### Numba version 
Numba python vie kompilovat python funkcie s dekoratororm @njit ak splnaju. Stale ale crashuje. 
### CUDA 


WORK IN PROGRESS

## Results 
