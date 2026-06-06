## Uczenie nienadzorowane.
Zadania w uczeniu nadzorowanym: 
- klasyfikacja
- regresja

Zadania w uczeniu nienadzorowanym: 
- klasteryzacja
- redukcja wymiarów
- estymacja gęstości rozkładu (mniej ważne)

#### Klasteryzacja
W uczeniu nienadzorowanym nie ma etykiet, klas. Są tylko punkty w przestrzeni. Chcemy je pogrupować tak, żeby podobne punkty (*bliskie pod względem cech*) były w tych samych grupach. Na tym polega klasteryzacja.

K-means to najprostszy algorytm klasteryzacji, grupowania. Polega po prostu na dystansach. Inicjalizuje się $K$ centroidów (grup, punktów centralnych klastra), np. losowo. Każdy punkt przypisuje się do najbliższego centroidu na podstawie odległości. Każdy centroid przesuwa się do średniej z pozycji wszystkich przypisanych do niego punktów. Przypisywanie do centroidu i przesuwanie powtarza się ustaloną $X$ liczbę razy albo aż się osiągnie oczekiwany wynik, czyli "centroidy będą się poruszały wystarczająco mało", co oznacza zbieżność.

![[Pasted image 20260606164346.png]]
![[Pasted image 20260606164351.png]]
![[Pasted image 20260606164356.png]]
![[Pasted image 20260606164400.png]]

Klasyfikacja wieloetykietowa oznacza, że jeden obiekt będzie miał kilka etykiet. Pojawia się cos podobnego w uczeniu nienadzorowanych, **Fuzzy c-Means**. "Klaster jest średnią instancji, ale jest poważone po przynależności"

![[Pasted image 20260606171453.png]]

**Claude wysryw bo Zyblewskiego odkleilo:**
```
Nie ma jednej uniwersalnej metody. Najpopularniejsza to elbow method — trenuje się k-means dla różnych wartości K i rysuje wykres sumy odległości punktów od centroidów (inercji). Szuka się "łokcia" — miejsca gdzie dodanie kolejnego klastra przestaje znacząco poprawiać wynik. Można też użyć silhouette coefficient i wybrać K z najwyższą wartością.

Warto mieć więcej klastrów niż klas, bo ta sama klasa może tworzyć kilka skupisk w różnych miejscach przestrzeni — jeden klaster mógłby je pomieszać.
```

Zazwyczaj zbiory, ktore sie klastruje mają etykiety. Na czas treningu zaklada się, że nie ma, ale służą do weryfikacji.

Klasteryzacja hierarchiczna występuje w dwóch wariantach:
1. **Agglomeratywna** **(bottom-up)** - każdy punkt zaczyna jako osobny klaster, następnie najbliższe klastry są kolejno łączone aż do uzyskania jednego drzewa.
2. **Divisive** **(top-down)** - wszystkie punkty zaczynają w jednym klastrze, który jest kolejno dzielony.

Metryki klasteryzacji:
- **Silhouette coefficient** - dla każdej próbki mierzy średnią odległość do innych próbek w tym samym klastrze versus średnią odległość do próbek z najbliższego innego klastra. Zakres od −1 do 1, wyżej znaczy lepiej. Problematyczny gdy klastry się nakładają.
- **Purity, completeness, homogeneity** - metryki oparte na etykietach (do weryfikacji, nie do treningu). Homogeneity i completeness są analogiczne do precision i recall w klasyfikacji.

**Claude wysryw:**
```
Wszystkie trzy wymagają etykiet, więc służą do weryfikacji, nie do treningu.

Homogeneity — czy każdy klaster zawiera tylko próbki jednej klasy? Klaster z samymi psami = idealna homogeneity.
Completeness — czy wszystkie próbki tej samej klasy trafiły do tego samego klastra? Wszystkie psy w jednym klastrze = idealna completeness.
Purity — dla każdego klastra bierze się najliczniejszą klasę i liczy ile procent klastra ona stanowi. Średnia po wszystkich klastrach. Prosta ale nie karze za rozdrobnienie — można uzyskać purity = 1 tworząc K = n klastrów (każdy punkt osobno).
```
#### Self learning
Self learning polega na tym ze uczy się np. klasyfikator, ale nie mamy ŻADNYCH etykiet. Trzeba jednak na czymś go wyuczyć. Sposobów jest kilka, opisano metodę oparta na **k-Means**.

Zamiast używać prawdziwych etykiet, generuje się je na bieżąco. W każdej iteracji:
- przepuszcza się cały zbiór przez sieć konwolucyjną, zbiera reprezentacje
- klastruje się k-Means na $K$ klastrów, gdzie $K=\text{n\_klas}$
- przypisania do klastrów stają się odpowiednikami etykiet
- na ich podstawie liczymy stratę i robimy propagację wsteczną

Sieć stopniowo uczy się reprezentacji, które są coraz lepiej separowalne - klastry stają się coraz czystsze, a pseudo-etykiety coraz trafniejsze.

Problem jest tylko taki, ze z góry zakładamy, że znamy liczbę klas, a nie zawsze tak jest.