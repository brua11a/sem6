Inferencja to w sumie po prostu wykorzystanie modelu, jego predykcja.

Sieci konwolucyjne
Pooling zmniejsza rozmiar danych wejściowych
Konwolucja to ????

Każdy obraz to macierz albo tensor. Operacja konwolucji polega na tym, że bierze się małe okno z jakimiś wartościami i się przechodzi po tym oknie. Fragment przemnaża się przez macierz konwolucji, dostaje się wynik.

Pooling np. bierze z każdego okna maksymalną wartość.

Stride to krok okna konwolucji. Padding dodaje piksele poza zdjęciem.  Konwolucja nie ma zmniejszać rozmiaru obrazu, ma to robić pooling. Zeby to się stało, trzeba podać i wziąć wartości spoza destination layer - właśnie po to jest padding. 