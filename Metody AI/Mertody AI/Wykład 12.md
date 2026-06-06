![[Pasted image 20260604185200.png]]
#### Data stream
Dane napływają potencjalnie ciągle i nieskończenie w czasie - nie są przechowywane w bazie ani żadnej strukturze, nigdy nie mamy pełnego zbioru. Strumienia nie przechowuje się, bo teoretycznie zajmowałby nieskończoną ilość miejsca. Często czas podjęcia decyzji, predykcji, testu ma duże znaczenie. Na strumieniu nie zrobi się analizy statystycznej, walidacji krzyżowej, nic nie działa.

#### Dryf koncepcyjny
Zmiany w strumieniu danych nazywamy dryfem koncepcyjnym. Nie chodzi o zmianę charakterystyki technicznej danych, ale o zmianę rozkładu lub zależności między cechami a etykietami.

Rodzaje dryfu:
1. **Nagły** - zmiana następuje w jednym punkcie czasu. Model wyuczony przed zmianą staje się natychmiast bezużyteczny.
2. **Inkrementalny** - rozkład zmienia się płynnie małymi krokami. Model powinien być na bieżąco aktualizowany, bo każdy kolejny krok różni się od poprzedniego.
3. **Gradualny** - dwa rozkłady współistnieją jednocześnie, zmieniają się tylko ich proporcje. Trudniejszy do wykrycia, bo model raz widzi stary rozkład, raz nowy. Przez pewien czas oba są obecne w danych.

![[Pasted image 20260606190920.png]]

#### Co robić ze strumieniem
Niezbalansowanie w strumieniu:
- **Static imbalance** - niezbalansowanie klas jest stałe w czasie, podobne do klasycznego problemu niezbalansowanych danych.
- **Dynamic imbalance** - proporcje klas zmieniają się w czasie wraz ze strumieniem, co dodatkowo utrudnia klasyfikację.

Na danych strumieniowych, ponownie, nie da się startyfikacji k-foldowej. Robi sie zamist tego **TestThenTrain**. Pierwszy chunk służy do trenowania, każdy kolejny jest najpierw predyktowany (test), potem służy do treningu.

Żeby wyliczyć metrykę, potrzebna jest predykcja i rzeczywista etykieta - problem jest taki, że w strumieniu dane mogą być nieoetykietowane lub mogą przychodzić z opóźnieniem. Moze być przydatny human in the loop i nie ma to sensu. Jak często jednak jest ten człowiek potrzebny? Czy musi cały czas siedzieć i etykietować? Poprzez metody statystyczne można np. wykryć ze coś jest nie tak i wtedy "dotrenować".

**Prequential** to wariant TestThenTrain, w którym zachowujemy część kontekstu z poprzedniego data stream. Wadą jest czas przetwarzania, dużo wolniejszy. Zaletą jest większa czułość, zależy od rozmiaru okna.

#### Klasyfikatory na danych strumieniowych
Jak częściej dokonujemy ewaluacji, szybciej wykryjemy dryf. Najczęściej w strumieniach stosuje się klasyfikatory, które pozwalają się "douczyć". Sieci neuronowe gdy się je doucza to zapomina stare dane - jest to tutaj dobre, bo strumień i tak idzie tylko do przodu, strumień sprzed dryfu nas nie obchodzi za bardzo.

Zdecydowana większość metod strumieniowych to metody zespołowe ([[Wykład 6 - bazowane na tym od Olgi]]). Zespoły są łatwe do douczenia, bo zamiast modyfikować poprzednie pod-klasyfikatory wystarczy dodać kolejny, nowy, wytrenowany na nowych danych. Jak może działać zespół klasyfikatorów w TestThenTrain? 
1. Trenuje się klasyfikator 1
2. Testuje się klasyfikatorem 1, trenuje się klasyfikator 2
3. Testuje się wszystkimi klasyfikatorami przez głosowanie/fuzję, trenuje się klasyfikator 3.

Inny pomysl - gorna granica liczby klasyfikatorow. Gdy dotrzeby do granicy, najslabszy/najstarszy się usuwa. Dzięki baggingowi można na spokojnie usuwać te klasyfikatory, żaden z nich nie jest krytyczny.

