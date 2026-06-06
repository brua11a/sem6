Inferencja to w sumie po prostu wykorzystanie modelu, żeby zdobyć jego predykcję.

Każdy obraz to macierz albo tensor. Operacja konwolucji polega na tym, że bierze się małe okno z jakimiś wartościami (filtr, kernel) i się przechodzi po tym obrazie. W każdej pozycji wykonuje się iloczyn element-po-elemencie między filtrem a fragmentem obrazu, a wyniki sumuje. Daje to jedną wartość w wyjściowej mapie cech (feature map). [[Wykład 7 (NIE NA KOLOSA)]]

**Stride** to krok, o jaki przesuwa się filtr. Większy stride → mniejsza feature map.
![[Pasted image 20260606152524.png]]

**Padding** dodaje piksele (zazwyczaj zera) wokół krawędzi obrazu, żeby filtr mógł operować również na pikselach brzegowych. Dzięki temu feature map może mieć taki sam rozmiar jak wejście.

![[Pasted image 20260606152509.png]]

**Pooling** zmniejsza rozmiar feature map. Np. max pooling bierze maksymalną wartość z każdego okna. To pooling, nie konwolucja, jest odpowiedzialny za redukcję rozmiaru danych.

![[Pasted image 20260606152500.png]]