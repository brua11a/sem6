Regresja liniowa i regresja logistyczna

Wykłady z sieci neuronowych. Chyba było na statystyce. Chodzi o to, że mamy punkty, mamy 2 zmienne (objaśnianą X i objaśniającą Y), 1 cechę, zadanie to dopasowanie prostej do punktów. Co jest modelem? Funkcja liniowa. Parametry są 2: a i b, bo y = ax+b, slope i intercept. "a mówi o ile jednostek y idziemy po przesunieciu x, b mowi gdzie przecina sie os Y na x=0".

Jak dopasowuje się prostą? Zazwyczaj poprzez metodę "najmniej kwadratów" (least squares). Można sobie polczyć odległość każdego punktu do prostej, znając X i Y każdego punktu i wzór prostej. Ruszając linią, oległości się zmieniają. Sum of squared residuals. Równanie prostej jest proste. Można sobie narysować wykres kwadratów "odległości" od wykresu w zależności od stałego a albo stałego b. Czy możemy sobie założyć a i b i po prostu szukać po kolei minimum? Da się ale to głupie. Można wyliczyć pochodną - szukamy punktu z nachyleniem == 0. 

Optymalizacja metodą gradientu prostego polega na tym, że zamiast sprawdzać wartości po kolei, chcemy to zrobić mądrze - zaczynamy od jakiejś wartości (slope\==1, intercept\==0). Sprawdza się kolejne wartości slope (a) tak, by wykonać minimum kroków. Im dalej jesteśmy od minimum, tym dłuższe są te kroki. Im bliżej jesteśmy oczekiwanego rozwiązania, tym częściej się sprawdza małe kroczki. 

Optymalizacja gradientu a i b to po prostu policzenie pochodnej 2x, raz a jest stale, raz b. Wykonuje się to ustaloną liczbę kroków aż osiągniemy wymagają dokładność. Ważne - pojawia się learning rate, który jest mnożnikiem kroku w gradiencie.

Regresja logistyczna. Rozwiązuje problem klasyfikacji binarnej. Nazywa się to regresją ale tak na prawdę jest to klasyfikator. Jest sigmoid. Odds != Probability. Jeśli "Odds" == 25% bo 1/4 to "Probablility" == 20% bo 1/5. 

*A probability of 0 is the same as odds of 0. Probabilities between 0 and 0.5 equal odds less than 1.0. A probability of 0.5 is the same as odds of 1.0. Think of it this way: The probability of flipping a coin to heads is 50%. The odds are “fifty: fifty,” which equals 1.0.*

*As the probability goes up from 0.5 to 1.0, the odds increase from 1.0 to approach infinity. For example, if the probability is 0.75, then the odds are 75:25, three to one, or 3.0.*

*If the odds are high (million to one), the probability is almost 1.00. If the odds are tiny (one to a million), the probability is tiny, almost zero.*

Żeby szanse byly symetryczne, liczy sie ln() od nich, bo 1/8 = 0.125 a 8/1 to 8, za to ich ln() są takie same ale odwrotne. Zakres zmieni się z 0:1 do -inf:inf, a sigmoida sie wyprosuje. Pozwala to wykonywać regresję liniową. Nie można tu policzyć odległości kwadratowej, bo zakres jest do inf. Można jednak rzutować punkty na prostą. Dzięki temu można odczytać wartości z ln() szans je odczytać. Daje to wzór ZGWALCE ZYBLEWSKIEGO. Suma kwadratów to funkcja straty - pojawi się później. Dla pozytywów jest to prawdopodobieństwo odczytane z sigmoidy. Dla negatywów to 1-prawdopodobieństwo. 

Konwolucja to zagnieżdżona pętla z macierzą przechodzącą po obrazie i wykonująca jedną operację matematyczną. "Sieć głęboka to taka co ma 3+ warstwy" apparently, chociaz Zyblewski się nie zgadza z tą definicją xd

Sieć neuronowa to sieć sztucznych neuronow (szoker). Sztuczny neuron to klocek liczący regresję liniową, under the hood logistyczną, nic więcej. inżycwela od 9 lat. W praktyce, sieć neuronowa ma diminishing return dla wiecej niz 3 warstw. Najważniejszym elementem sieci jest ekstrakcja cech - połączony specyfikacją. Sieć nie operuje na cechach, które człowiek rozumie, troche black box. Rozrózniamy deep learning po tym, że i guess mniej cech jest rozumialnych i mniej robi czlowiek. Wartości zbioru danych beda inne w kazdej epoce + duzo warstw neuronow wymagane przez architekture. 

