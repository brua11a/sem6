## Regresja liniowa i regresja logistyczna

#### O co chodzi
Wykłady z sieci neuronowych. Chodzi o to, że mamy punkty, każdy z nich ma 2 zmienne (*objaśniającą* $X$ i *objaśnianą* $Y$). Zadanie to dopasowanie prostej do punktów.
Co jest modelem? Funkcja liniowa, $f(x, \theta) = y = ax + b$. Parametry $\theta$ są 2: $a$ i $b$, reprezentuja *slope* i *intercept*.

*Parametr $a$ mówi o ile jednostek $y$ idziemy po przesunieciu $x$, parametr $b$ mowi gdzie przecina sie os Y na $x=0$.*

![[Pasted image 20260606115659.png]]

#### Jak dopasowuje się prostą do punktów?
Zazwyczaj poprzez metodę "najmniej kwadratów" (*least squares*). Można sobie polczyć odległość każdego punktu do prostej, znając $X$ i $Y$ każdego punktu i wzór prostej. Ruszając linią, odległości się zmieniają. Liczy się *sum of squared residuals*. Można sobie narysować wykres kwadratów "odległości" od wykresu w zależności od stałego $a$ albo stałego $b$.

![[Pasted image 20260606121016.png]]

Czy możemy sobie założyć $a$ i $b$ i po prostu szukać po kolei minimum? Da się ale to głupie. Można wyliczyć pochodną cząstkową - szukamy punktu z nachyleniem = 0, lokalne ekstremum (też z matury pamietamy). 

Optymalizacja metodą gradientu prostego polega na tym, że zamiast sprawdzać wartości po kolei, chcemy to zrobić mądrze - zaczynamy od jakiejś wartości ($\text{slope}=1$, $\text{intercept}=0$). Sprawdza się kolejne wartości slope ($a$) tak, by wykonać minimum kroków. Im dalej jesteśmy od minimum, tym dłuższe są te kroki. Im bliżej jesteśmy oczekiwanego rozwiązania, tym częściej się sprawdza małe kroczki. "Kierunek" będzie wyznaczany przez pochodną funkcji straty.

```
The basic intuition behind gradient descent can be illustrated by a hypothetical scenario. People are stuck in the mountains and are trying to get down (i.e., trying to find the global minimum). There is heavy fog such that visibility is extremely low. Therefore, the path down the mountain is not visible, so they must use local information to find the minimum. They can use the method of gradient descent, which involves looking at the steepness of the hill at their current position, then proceeding in the direction with the steepest descent (i.e., downhill). If they were trying to find the top of the mountain (i.e., the maximum), then they would proceed in the direction of steepest ascent (i.e., uphill). Using this method, they would eventually find their way down the mountain or possibly get stuck in some hole (i.e., local minimum or saddle point), like a mountain lake. However, assume also that the steepness of the hill is not immediately obvious with simple observation, but rather it requires a sophisticated instrument to measure, which the people happen to have at that moment. It takes quite some time to measure the steepness of the hill with the instrument. Thus, they should minimize their use of the instrument if they want to get down the mountain before sunset. The difficulty then is choosing the frequency at which they should measure the steepness of the hill so as not to go off track.

In this analogy, the people represent the algorithm, and the path taken down the mountain represents the sequence of parameter settings that the algorithm will explore. The steepness of the hill represents the slope of the function at that point. The instrument used to measure steepness is differentiation. The direction they choose to travel in aligns with the gradient of the function at that point. The amount of time they travel before taking another measurement is the step size.
```

Optymalizacja gradientu $a$ i $b$ to po prostu policzenie pochodnej 2x, raz $a$ jest stale, raz $b$. Wykonuje się to ustaloną liczbę kroków aż osiągniemy wymagają dokładność. Ważne - pojawia się learning rate, który jest mnożnikiem kroku w gradiencie.

#### Regresja logistyczna
Rozwiązuje problem klasyfikacji binarnej. Pozwala wyniki z zakresu $(-\infty;\infty)$ rzucić na wykres, który ograniczy je prawdopodobieństwa z zakresu $(0;1)$
Nazywa się to regresją ale tak na prawdę jest to klasyfikator. Często opisywany przez funkcję sigmoid. 

**Claude wysryw:**
```
Sigmoidа właśnie to robi — ściska dowolną liczbę z (−∞, +∞) do (0, 1). Więc model w środku nadal robi regresję liniową (liczy `ax + b`), ale wynik przepuszcza przez sigmoidę, żeby dostać prawdopodobieństwo. Jeśli wyjdzie > 0,5 → klasa 1, jeśli < 0,5 → klasa 0.

Krótko: regresja logistyczna = regresja liniowa + sigmoida na końcu = klasyfikator binarny.
```

![[Pasted image 20260606142345.png]]

==Dygresja: Odds != Probability. Jeśli "Odds" == 25% bo 1/4 to "Probablility" == 20% bo 1/5.==
- Probability mieści się w zakresie $[0;1]$. Jest to $P = \frac{\text{n\_sukcesów}}{\text{m\_wszystkich}}$
- Odds ma wartości z zakresu $[0;\infty)$. Jest to $O = \frac{\text{n\_sukcesów}}{\text{m\_porażek}}$

```
A probability of 0 is the same as odds of 0. Probabilities between 0 and 0.5 equal odds less than 1.0. A probability of 0.5 is the same as odds of 1.0. Think of it this way: The probability of flipping a coin to heads is 50%. The odds are “fifty: fifty,” which equals 1.0.

As the probability goes up from 0.5 to 1.0, the odds increase from 1.0 to approach infinity. For example, if the probability is 0.75, then the odds are 75:25, three to one, or 3.0.

If the odds are high (million to one), the probability is almost 1.00. If the odds are tiny (one to a million), the probability is tiny, almost zero.
```

Żeby szanse (odds) były symetryczne, liczy się logarytm o podstawie $e$ ($ln$) od nich, bo 1/8 = 0.125 a 8/1 to 8, za to ich $ln$ są takie same, ale odwrotne ($ln(\frac{1}{8})=-ln(8)$). Zakres zmieni się z $0:1$ do $-\infty:\infty$, a sigmoida się wyprostuje. Pozwala to wykonywać regresję liniową.

Nie można tu policzyć odległości kwadratowej, bo zakres jest do $\infty$. Można jednak rzutować punkty na prostą. Dzięki temu można odczytać wartości z $ln$.

Ta suma kwadratów to funkcja straty. Dla pozytywów jest to prawdopodobieństwo odczytane z sigmoidy. Dla negatywów to 1-prawdopodobieństwo. 

**Claude wysryw sequel:**
```
W regresji liniowej liczyliśmy pionową odległość punktu od prostej i ją kwadratowaliśmy. Tu nie możemy tak samo, bo operujemy na log-odds (zakres −∞ do +∞) i punkty są binarne (0 albo 1), więc "odległość" nie ma tu sensu.
Funkcja straty (log-loss):
Zamiast tego pytamy — jak bardzo model się mylił? Dla każdego punktu:

jeśli rzeczywista klasa to 1 (pozytyw): strata = −ln(p), gdzie p to prawdopodobieństwo z sigmoidy. Im wyższe p (model był pewny i miał rację), tym mniejsza strata.
jeśli rzeczywista klasa to 0 (negatyw): strata = −ln(1−p). Model powinien dawać niskie p, więc 1−p powinno być wysokie.

Sumuje się to po wszystkich punktach — to jest log-loss, właściwa funkcja straty dla regresji logistycznej.
```

#### Konwolucja
Konwolucja to zagnieżdżona pętla z macierzą przechodzącą po obrazie i wykonująca jedną operację matematyczną. "Sieć głęboka to taka co ma 3+ warstwy" apparently, chociaż Zyblewski się nie zgadza z tą definicją.

![[Pasted image 20260606152044.png]]

Sieć neuronowa to sieć sztucznych neuronow (szoker). Sztuczny neuron to klocek liczący regresję liniową, under the hood logistyczną, nic więcej. inżycwela od 9 lat. W praktyce, sieć neuronowa ma diminishing return dla wiecej niz 3 warstw. Najważniejszym elementem sieci jest ekstrakcja cech - połączony specyfikacją. Sieć nie operuje na cechach, które człowiek rozumie, troche black box. Rozrózniamy deep learning po tym, że i guess mniej cech jest rozumialnych i mniej robi czlowiek. Wartości zbioru danych beda inne w kazdej epoce + duzo warstw neuronow wymagane przez architekture. 

