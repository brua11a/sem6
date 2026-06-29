#### Protokoły eksperymentalne
Do eksperymentu potrzebne są dane, hipoteza, metodologia/założenia (parametry, algorytmy...), podział danych, metryka, analiza statystyczna.

![[Pasted image 20260604104000.png]]
## Metryki

https://developers.google.com/machine-learning/crash-course/classification/accuracy-precision-recall

#### Dokładność (Accuracy) 
Dokładność, "na przykład w 70% przypadków mieliśmy rację", czyli procent poprawnych predykcji. Można rozumieć jako sumę przypadków TP (True Positive, poprawnie przewidziano klasę pozytywną) i TN (True Negative, poprawnie przewidziano klasę negatywną) podzieloną przez sumę wszystkich przypadków ($ALL = TP+FP+TN+FN$).

$\text{accuracy} = \frac{TP+TN}{ALL}$

Accuracy jest mylące przy niezbalansowanych danych - model, który zawsze na chama przewiduje klasę większościową będzie miał duże accuracy, chociaż będzie w praktyce bezużyteczny.

*Accuracy is the proportion of all classifications that were correct, whether positive or negative.*

#### Czułość (Recall, True Positive Rate)
Jaki procent klasy pozytywnej rozpoznaliśmy poprawnie. Czyli proporcja TP (poprawnie wykryto klasę pozytywną) do TP+FN (poprawnie wykryto klasę pozytywną + niepoprawnie wykryto klasę negatywną, a powinno wykryć pozytywną). Iloraz ze wszystkich próbek poprawnie przypisanych do klasy pozytywnej przez wszystkie rzeczywiste instancje klasy pozytywnej.

$\text{recall} = \frac{TP}{TP+FN}$

Przykładowo, eksperyment. Mamy 100 instancji, z czego 2 są pozytywne i 98 jest negatywnych. "Na chama" uznamy, że pozytywne są wszystkie.

Recall wtedy będzie będzie równy 100%, bo wszystkie instancje klasy pozytywnej zostały poprawnie zidentyfikowane. 98% próbek zostanie źle sklasyfikowanych, ale wszystkie probki klasy pozytywnej zostały sklasyfikowane dobrze. 

*Recall or Sensitivity measures how many of the actual positive cases were correctly identified by the model. It is important when missing a positive case (false negative) is more costly than false positives.*

Metryka podstawowa - z niej się "składa" inne.
#### Precyzja 

Proporcja poprawnych klasyfikacji pozytywnych do wszystkich klasyfikacji pozytywnych. Czyli proporcja TP do TP+FP.

$\text{precision} = \frac{TP}{TP+FP}$

*It measures how many of the positive predictions made by the model are actually correct. It's useful when the cost of false positives is high such as in medical diagnoses where predicting a disease when it’s not present can have serious consequences.*

#### Miss rate
Odbicie recall, rzadko spotykane.

$\text{miss rate}=1-\text{recall}$
#### Specificity (True Negative Rate)
Jaki procent rzeczywistej klasy negatywnej wykryto poprawnie. Czyli taki recall ale dla klasy negatywnej.

$\text{specificity} = \frac{TN}{TN+FP}$

#### Fallout
Odwrotność specificity. Czyli taki miss rate dla klasy negatywnej.

$\text{fallout}=1-\text{specificity}$

| Metryka     | Wzór                     | Co mierzy                                                            |
| ----------- | ------------------------ | -------------------------------------------------------------------- |
| Accuracy    | $\frac{TP+TN}{ALL}$      | Procent wszystkich poprawnych predykcji                              |
| Recall      | $\frac{TP}{TP+FN}$       | Procent wykrytych pozytywnych z wszystkich rzeczywistych pozytywnych |
| Precision   | $\frac{TP}{TP+FP}$       | Procent poprawnych wśród wszystkich przewidzianych pozytywnych       |
| Specificity | $\frac{TN}{TN+FP}$       | Procent wykrytych negatywnych z wszystkich rzeczywistych negatywnych |
| Miss rate   | $1 - \text{recall}$      | Procent przeoczonych pozytywnych                                     |
| Fallout     | $1 - \text{specificity}$ | Procent przeoczonych negatywnych                                     |

___
## Złożone meteyki
#### BAC (Balanced Accuracy Score)
Średnia arytmetyczna recall i specificity. "Na to można patrzeć zawsze, czy problem jest zbalansowany czy nie".
$BAC=\frac{\text{Recall}+\text{Specificity}}{2}$

#### Gmean (Geometric Mean Score)
Pierwiastek iloczynu recall i specificity. Nie powie więcej niż powie BAC.
$G_{mean}=\sqrt{\text{Recall}*\text{Specificity}}$

#### F-beta
Średnia harmoniczna recall i precyzji. Beta $\beta$ to waga dla tych parametrów:
- $\beta=1$ oznacza, że recall i precision będą równoważne
- $\beta>1$ oznacza, że recall będzie miał większe znaczenie
- $\beta<1$ oznacza, ze precision będzie miało większe znaczenie

Silnie krytykowana metryka przez tą dodatkowa wage. Często ludzie liczą $\beta=1$ i elo. Nie zawsze jest to dobre. Dobór $\beta$ powinien zależeć od kontekstu problemu.
$F_\beta=(1+\beta^2)*\frac{\text{Precision}*\text{Recall}}{\beta^2*\text{Precision}+\text{Recall}}$

## Benchmark datasets
Zazwyczaj korzysta się z dostępnych zbiorów benchmarkowych, które są wykrzystywane od lat. Żeby sprawdzić, czy algorytm jest lepszy od innego, nie chcemy tego badać na jednym zbiorze bo to mało miarodajne. Nie koncetrujemy się bardzo na jednym, konkretnym zbiorze danych, tylko na wielu różnych - różne liczby cech, różne typy cech, różne liczby próbek.

Na produkcji zazwyczaj już można skupić się na o wiele węższym zakresie, bo interesuje nas konkretny problem.

#### Dane syntetyczne
Używa się ich rzadziej. Ciężko sprawić, by rzeczywiście odzwierciedlały prawdziwe problemy. Przydają się przy danych strumieniowych - napływających w czasie rzeczywistym. Pojawia się tam *dryf koncepcji*, który sprawia, że cała przestrzeń się przesuwa. Oznacza to, że nawet po nauczeniu się jakiegoś sensownego thresholdu po tygodniu może być źle. Stare dane nie muszą odzwierciedlać tych nowych ale o tym wiecej w [[Wykład 12]]. 

## Trening
#### "Sztywny" podział vs k-Fold
Jako sztywny podział test-trening rozumiemy wzięcie oryginalnego datasetu i jednokrotnym "pokrojeniu" go na dane treningowe i testowe. Model trenuje się na danych treningowych a potem na wytrenowanym modelu wykonuje predykcje, które są walidowane zbiorem testowym. Nie jest to rozwiązanie rzetelne ani zbalansowane.

![[Pasted image 20260604185607.png]]

O wiele lepszy jest k-Fold Cross-Validation. Zbiór jest dzielony na $k$ równych *foldów*, model jest trenowany $k$ razy, za każdym razem inny fold jest testem, reszta treningowym. Problemem jest tylko to, że cała klasa może zamknąć się w jednym foldzie. Rozwiązanie to **Stratified** k-Fold Cross Validation, gdzie podział klas w foldach odpowiada temu w oryginalnych zestawach danych. **Repeated** Stratified k-Fold Cross Validation używać zawsze.

![[Pasted image 20260604185453.png]]
![[Pasted image 20260604185518.png]]

#### Leave-One-Out
Specjalna walidacja krzyżowa używana dla małych zbiorów danych. Występuje, gdy $k=n$, czyli liczba próbek jest równa liczbie foldów, zatem każdy fold składa się z jednej próbki. Dla każdego splitu tylko jeden z nich to test a wszystko inne to trening.

![[Pasted image 20260604190326.png]]

Nie da się policzyć ani średniej, ani odchylenia ani nic - na końcu jest tylko jeden wynik na fold. Używa się tylko gdy zestawy danych są mega małe - 20, 50 próbek. Normalne metody dadzą wtedy gówniane wyniki. "Bierzemy tyle ile się da do treningu i liczymy na to ze klasyfikator nauczy się czegokolwiek".

Liczbę k-Foldów wybiera się na podstawie rozmiaru zbioru danych. Im większy zbiór tym mniejsze k wystarczy. 
*The choice of K affects the trade-off between bias and variance:*
*Small K (e.g., K=2 or K=5): Faster computation with increased variance in performance estimates.*
*Large K (e.g., K=10 or K=n, where n is the size of the dataset): Lower variance but higher computational cost. K = n corresponds to Leave-One-Out Cross Validation (LOOCV).*

Przykład: K=5 oznacza, że dzielisz zbiór na 5 równych części i trenujesz model 5 razy. Każdy fold ma wtedy 20% danych jako test i 80% jako trening.