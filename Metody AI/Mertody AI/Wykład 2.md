Obrazy -> dyskretne sygnały cyfrowe
Tabele są trudniejsze od zdjęć do przetworzenia dla ML - zdjęcia są jedną z prostszych form. Tabele mają w sobie różnorodne typy danych - są heterogeniczne, za to obrazy są homogeniczne, jeden typ danych. Zdjęcie jest macierzą (tensorem), zakres 0-255 uint_8. W danych tabularycznych jest słabsza korelacja cech niż w przypadku danych sygnałowych - cechy mogą być skorelowane lub niezależne, brakuje informacji o pozycji. Wygenerowanie sensownej tabeli jest trudniejsze od wygenerowania filmu.

#### Podejścia oparte na encode'owaniu/transformacji danych
Kategorie można np. przerobić na ENUM. Są podejścia jednowymiarowe i wielowymiarowe. Wielowymiarowe są związane z uczeniem głębokim, ale to mniejsza., nie dotyczy kursu. Polega na tym, że dla danych tabelarycznych z każdego wzorca robi się obraz a potem używa się sieci głębokich. Każdy wiersz zamienia się w obraz xd. Pozwala ominąć braki danych i String - nie trzeba encode'ować.

Label encoding -> każda kategoria zmienia się w integer. To można zawsze, "tego zepsuć się nie da", no chyba, że dane są niezbalansowane - klasa mniejszościowa musi mieć etykietę 1. Wprowadza to uporządkowanie do kategorii, a one nie zawsze powinny być uporządkowane. "Problem jest jak ktoś zamieni np. Indie, USA na liczby 0, 33 przez co model może uznac ze USA jest lepsze od Indii bo jest wyższa liczba"

One-hot encoding -> dla każdej kategorii dodatkowa cecha. Czyli kolumna zostanie zamieniona na kolumnę binarnych dopasowań, z (48842, 1) na (48842, 16) jeśli jest 16 klas. Wtedy nie ma takiego uporządkowania. Pojawia się dużo cech - złożoność obliczeniowa zależy od ilości cech. Z tą metodą robi się problem jak tym zencode'uje się wszystko - im więcej wymiarów jest danych tym ciężej, jeśli cech jest więcej niż próbek to generalizacja jest bardzo trudna. 

Binary encoding -> podobne ale mnie kolumn. Czyli 16 kategorii można zamienić na 4, bo mieści się to w 4 bitach.

Target encoding -> kategoria przyjmuje średnia wartość etykiety. 

Hash-based encoding -> wartość zhashowana.

#### Inputacja
Na nieistniejących wartościach nie wytrenuje się niczego, dlatego trzeba te dane uzupełnić - właśnie to to inputacja. Najczęściej będą to NaN. Jeśli niepełnych danych jest mało to można po prostu usunąć ten wzorzec. Ewentualnie można wstawić średnią/medianę/modę. Nie ma klasyfikatora, metody w ML, która jest "najlepsza" - na każde pytanie odpowiedzią jest "zależy".

"Normalizacja" w kontekście inputu może być:
- normalizacja standardowa cech (po kolei kolumny), bierze się wartości cech, zapisuje się je jako średnia + odchylenie - potem średnia będzie "w zerze", a odchylenie będzie liczbą ujemną lub dodatnią
- normalizacja przedziałowa, nieważne co wszystkie wartości ogranicza się do przedziału
- normalizacja L2 wykonywana jest po wierszach, używana w metodach odległosciowych, pierwiastek kwadratowy z sumy kwadratów

Jeśli cech jest za dużo i one przeszkadzają to należy je zredukować. 

#### Selekcja i ekstrakcja
Selekcja to wybranie podzbioru cech, ekstrakcja to "wyliczenie" nowych cech na podstawie oryginalnych cech - przekształcenie na mniej wymiarów. Podczas ekstrakcji te "nowe" cechy nie są już interpretowalne - to wada jeśli chce się zobaczyć nie tylko decyzję ale i "rozumowanie" modelu. 

Prosta selekcja to `SelectKBest` (podejście filtrowe). Wykorzystuje się metody statystyczne, żeby wyliczyć sobie "korelację cechy z klasą". Dla każdej kolumny zostanie policzony score, zachowuje się te o największej wartości. Wiemy wtedy które kolumny są wartościowe, które mają małe znaczenie. Takie filtry nie badają korelacji pomiędzy cechami - to złe. 

Do ekstrakcji najczęściej służy PCA. Podaje się liczbę komponentów (nowych cech), które chcemy uzyskać lub procent objaśnionej wariancji - ile oryginalnej informacji zachowano. Minimum 70% jest w porządku zazwyczaj. Na przykład tabela 8 cech zredukowana do 1 komponentu może nieść 88% informacji, 2 komponenty 95% itd.

#### Miary trudności problemów
Jest 6-7 kategorii. Część zależy od cech, część od sąsiedztwa... Można wtedy policzyć 20 miar i zobaczyć jak trudny jest zbiór pod konkretnym względem.