Bardziej poglądowo
Polecany po raz kolejny jest artykuł *How to design the fair experimental classifier evaluation*.
## Testy normalności rozkładu
Sprawdza, czy rozkład jest normalny. Testy parametryczne obchodzi to, jaki jest rozkład - najlepiej jeśli jest on normalny. Testów normalności jest masa, sprawdza się najczęściej Shapiro-Wilk, rzadziej Kolmogorov-Smirnov. Jeśli testu nie obchodzi rozkład, to mówi się o testach nieparametrycznych.

**UWAGA: dla klasyfikatorów, gdzie jest wiele zbiorów i wiele klasyfikatorów używa się wilcoxona signed.**
## Powszechnie używane testy
#### Dwa klasyfikatory na jednym zbiorze:
- **(Corrected) Student's T-test** - parametryczny
- **5x2 / Mann-Whitney** - nieparametryczny

#### Dwa klasyfikatory na wielu zbiorach:
- **Wilcoxon signed-rank test** 
  >*The Wilcoxon Signed Rank Test is a non-parametric statistical test used to compare two related groups. It is often applied when the assumptions for the paired t-test (such as normality) are not met. This test evaluates whether there is a significant difference between two paired observations, making it especially useful for non-normally distributed or ordinal data.*

#### Wiele klasyfikatorów na wielu zbiorach:
- **Friedman's rank test**
  >*Friedman Test is a non-parametric method to determine the significance of differences between multiple (M) classification algorithms evaluated over multiple (N) datasets.*
- **Nemenyi post hoc test**
  >*The Friedman Test is used to find whether there exists a significant difference between the means of more than two groups. In such groups, the same subjects show up in each group. If the p-value of the Friedman test turns out to be statistically significant then we can conduct the Nemenyi test to find exactly which groups are different. This test is also known as Nemenyi post-hoc test.*

**Claude wystryw**
```
Praktycznie:
- sprawdzasz normalność (Shapiro-Wilk)
- jeśli rozkład normalny → możesz użyć parametrycznego (T-test)
- jeśli nie → używasz nieparametrycznego (Mann-Whitney, Wilcoxon)

Dla klasyfikatorów ML prawie zawsze używa się nieparametrycznych — wyniki rzadko mają rozkład normalny, a Wilcoxon jest bezpieczniejszym wyborem.
```

| Scenariusz                          | Parametryczny                | Nieparametryczny            |
| ----------------------------------- | ---------------------------- | --------------------------- |
| 2 klasyfikatory, 1 zbiór            | (Corrected) Student's T-test | 5x2 / Mann-Whitney          |
| 2 klasyfikatory, wiele zbiorów      | —                            | Wilcoxon signed-rank        |
| Wiele klasyfikatorów, wiele zbiorów | —                            | Friedman → Nemenyi post-hoc |
#### Jakie będą testy
1. **Paired - Parowy** (NIE musi być na parach klasyfikatorów)
   >Dla prób zależnych. Próby są zależne, gdy mierzy się "to samo" w dwóch warunkach, na przykład 2 klasyfikatory trenowane i testowane na tych samych foldach. Wyniki są powiązane.
2. **Unpaired** 
   >Dla prób niezależnych. Próby są niezależne, gdy nie ma żadnego powiązania między pomiarami. Rzadkie w ML, może to być sytuacja w której dwa klasyfikatory były trenowane i testowane na zupełnie innych zestawach danych.
3. **Paired != Pairwise (pairwise to jest rzeczywiście "w parach")**
   >Np. masz A, B, C → porównujesz A vs B, A vs C, B vs C. Każdy z każdym.

Zazwyczaj testy, nadzorowanie badania są zależne, czyli wykonuje się testy paired. Wyniki klasyfikatorów mogę być różne ale działające na tych samych wzorcach. 

$\alpha$ to pewna tolerancja błędu, alfa na 5% oznacza, że wynik będzie na 95% prawdziwy. Właściwie, akceptujemy 5% na szpont (*odrzucenie hipotezy zerowej gdy ta jest prawdziwa*). 5% to standard.

Na potrzeby porównywania klasyfikatorów, wykorzystuje się średnie dla konkretnich datasetów wyliczone poprzez uśrednienie wyników foldów - znane z labów. Czasem pojawiają się rankingi. Metody rankingowe sprawdzają, na którym "miejscu" jest dany klasyfikator - znane z biometrii. Pozwala to unikać sytuacji, w której jeden z klasyfikatorów ma świetny średni wynik bo raz wyszedł wyśmienicie a zazwyczaj chujowo.

#### Wiele zbiorów, wiele klasyfikatorów
Wykorzystuj Friedmann, z 20 metod i z 30 datasetów. Przedstawia się różnice w postaci diagramu wartości krytycznych, gdzie są przedstawiane średnie rangi. Jeżeli rankingi dwóch metod mieszczą się w różnicy krytycznej, to różnica między nimi nie jest statystycznie znacząca. 

![[Pasted image 20260604201911.png]]
