Analiza statystyczna 
W przyszłym tygodniu nie ma wykładu bo Zyblewski jedzie do Włoch!!!

Bardziej poglądowo
Polecany po raz kolejny jest artykuł *How to design the fair experimental classifier evaluation*.

Testy normalności rozkładu - sprawdza, czy rozkład jest normalny. Testy parametryczne obchodzi to, jaki jest rozkład - najlepiej jest, jeśli jest on normalny. Testów jest masa, używa się Shapiro-Wilk (najczęściej) i Komogorov-Smirnov. 

Powszechnie używane testy:

Dwa klasufolkatorzy na jednym zbiorze:
- (Corrected) Student's T-test - parametryczny lub nieparametryczny
- 5x2 / Mann-Whitney

Dwa klasyfiaktory na wielu zbiorach:
- Wilcoxon rank-sum

Wiele klasyfikatorów na wielu zbiorach:
- Friedmamn's rannk test
- Nemenyi post hoc test
Warte rozważenia gdy klasyfikatrów jest masa, robi się wykresy różnicy krytycznej.

Paired == Parowy (NIE musi byc na parach klasyfikatorów) == Dla prób zależnych
Unpaired == Dla prób niezależnych
Paired != Pairwise (to jest rzeczywiście "w parach")

Zazwyczaj testy, nadzorowanie badania są zależne. Wyniki klasyfikatorów mogę być różne ale działające na tych samych wzorcach. 

$\alpha$ to pewna tolerancja błędu, alfa na 5% oznacza, że wynik będzie na 95% prawdziwy. 5% to standard.

Na potrzeby porównywania klasyfikatorów, wykorzystuje się średnie dla konkretnich datasetów wyliczone poprzez uśrednienie wyników foldów - axis 2. Czasem pojawiają się rankingi - metody rankingowe sprawdzają, na którym "miejscu" jest dany kalsyfikator, co pozwala unikać sytuacji, w której jeden z kalsyfikatorów ma świetny średni wynik bo raz wyszedł wyśmienicie a zazwyczaj chujowo.

Wiele zbiorów, wiele klasyfikatorów: Wykorzystuj Friedmann, z 20 metod i z 30 datasetów. Przedstawia się różnice w postaci diagramu wartości krtyycznych, gdzie są przedstawiane średnie rangi. Jeżeli rankingi dwóch metod mieszczą się w różnicy krytycznej, to różnica między nimi nie jest statystycznie znacząca. 

