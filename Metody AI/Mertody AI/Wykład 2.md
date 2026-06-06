#### Przetwarzanie różnych modalności w ML
Tabele są trudniejsze od zdjęć do przetworzenia dla algorytmów ML. W sumie to obrazy są jedną z prostszych form informacji. Są to dyskretne sygnały cyfrowe (właściwie siatka wartości). Format jest spójny. Można założyć, że zdjęcie jest macierzą (tensorem), gdzie każdy punkt mieści się w zakresie 0-255 uint_8.

Tabele mają w sobie różnorodne typy danych - są heterogeniczne, za to obrazy są homogeniczne, zawierają jeden typ danych. W danych tabularycznych jest słabsza korelacja cech niż w przypadku danych sygnałowych - cechy mogą być skorelowane lub niezależne, brakuje informacji o pozycji. Wygenerowanie sensownej tabeli jest trudniejsze od wygenerowania filmu.

#### Podejścia oparte na encode'owaniu/transformacji danych
Jest kilka sposobów na przetworzenie danych tabularycznych. Są podejścia jednowymiarowe i wielowymiarowe.

Dla jasności, kategoria != etykieta. Kategoria to możliwa wartość cechy wejściowej, czyli zawartość kolumny w tabeli. Etykieta to klasa przypisana samplowi.

**Podejścia wielowymiarowe**
Są związane z uczeniem głębokim, ale to nie dotyczy kursu. Polega na tym, że dla danych tabelarycznych z każdego wzorca robi się obraz a potem używa się sieci głębokich. W praktyce każdy wiersz zamienia się w obraz xd

**Podejścia jednowymiarowe**
1. **Label encoding**
   >Każda kategoria zmienia się w integer. To można robić zawsze, "tego zepsuć się nie da". Wyjątek gdy dane są niezbalansowane - klasa mniejszościowa musi mieć etykietę 1. Label encoding wprowadza uporządkowanie do kategorii, a one nie zawsze powinny być uporządkowane. "Problem jest jak ktoś zamieni np. Indie, USA na liczby 0, 33 przez co model może uznac ze USA jest lepsze od Indii bo jest wyższa liczba"
2. **One-hot encoding**
   >Dla każdej kategorii dopisywana jest dodatkowa cecha, czyli jeśli jest 16 możliwych kategorii/etykiet, to powstanie 16 nowych kolumn *binarnych dopasowań*, gdzie większość będzie pusta. Z shape np. (48842, 1) zrobi się (48842, 16) jeśli jest 16 klas. Wtedy nie ma problemu uporządkowania z wcześniej. Tradeoff jest taki, ze pojawia się dużo cech - złożoność obliczeniowa zależy od ilości cech. Z tą metodą robi się problem jak tym zencode'uje się wszystko. Jeśli cech jest więcej niż próbek to generalizacja jest bardzo trudna.

![[Pasted image 20260604100320.png]]

3. **Binary encoding**
   >Podobne ale mniej kolumn, nie tworzy się nowej kolumny dla każdej cechy. Zamiast tego "łączy" się bity w bitmapach. Czyli 16 kategorii  i 16 kolumn z one-hot można zamienić na 4, bo liczba 16 mieści się to w 4 bitach.
4. **Target encoding**
   >Kategoria jest zastępywana średnią wartością etykiety dla tej kategorii
5. **Hash-based encoding**
   >Kategoria hashowana do wektora o stałym rozmiarze.

#### Imputacja
Na nieistniejących wartościach nie wytrenuje się niczego, dlatego trzeba te dane uzupełnić - właśnie to jest **imputacja**. Jeśli niepełnych danych jest mało to można po prostu usunąć te wzorce. Ewentualnie można wstawić średnią/medianę/modę w nieuzupełnione pola.

Nie ma klasyfikatora, metody w ML, która jest "najlepsza" - na każde pytanie odpowiedzią jest "zależy".

**Normalizacja** w kontekście inputu może oznaczać:
1. Normalizację standardową cech (po kolei kolumny)
   >Każdą $x :=$ wartość w kolumnie przekształca się jako $z = \frac{(x-\text{avg})}{\text{std}}$. Średnia kolumny wtedy zawsze będzie w 0, a odchylenie od tego będzie liczbą ujemną lub dodatnią. Po co? Żeby cechy o różnych skalach (np. wiek 0–100 i zarobki 0–100000) nie dominowały jedne nad drugimi w modelu. Po standaryzacji wszystkie kolumny są "na tej samej skali".
2. Normalizacja przedziałowa
   >Nieważne co wszystkie wartości ogranicza się, skaluje do przedziału.
3. Normalizacja L2
   >Wykonywana jest po wierszach, używana w metodach odległosciowych. Pierwiastek kwadratowy z sumy kwadratów wszystkich wartości w danym wierszu.

Jeśli cech jest za dużo i one przeszkadzają to należy je zredukować. 

#### Selekcja i ekstrakcja
Selekcja to wybranie podzbioru cech. Ekstrakcja to "wyliczenie" nowych cech na podstawie oryginalnych cech - przekształcenie na mniej wymiarów. Po ekstrakcji te "nowe" cechy nie są już interpretowalne - to wada jeśli chce się zobaczyć nie tylko decyzję ale i "rozumowanie" modelu. 

Prosta selekcja to `SelectKBest` (podejście filtrowe). Wykorzystuje się metody statystyczne, żeby wyliczyć sobie "korelację cechy z klasą". Dla każdej kolumny zostanie policzony score, zachowuje się te o największej wartości. Wiemy wtedy które kolumny są wartościowe, które mają małe znaczenie. Takie filtry nie badają korelacji pomiędzy cechami - to złe. 

Do ekstrakcji najczęściej służy PCA. Podaje się liczbę komponentów (nowych cech), które chcemy uzyskać lub procent objaśnionej wariancji - ile oryginalnej informacji zachowano. Minimum 70% jest w porządku zazwyczaj. Na przykład tabela 8 cech zredukowana do 1 komponentu może nieść 88% informacji, 2 komponenty 95% itd.

#### Miary trudności problemów
Jest 6-7 kategorii. Część zależy od cech, część od sąsiedztwa... Można wtedy policzyć 20 miar i zobaczyć jak trudny jest zbiór pod konkretnym względem.