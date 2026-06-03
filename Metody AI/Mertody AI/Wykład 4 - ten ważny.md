Protokoły eksperymentalne

Do eksperymentu potrzebne są dane, hipoteza, metodologia/założenia (parametry, algorytmy...), podziale danych, metryka, analiza statystyczna.

#### Metryki
**Dokładność - np. "w 70% mieliśmy rację"**
`Accuracy is a fundamental metric used for evaluating the performance of a classification model. It tells us the proportion of correct predictions made by the model out of all prediction`
$\text{accuracy()} = \frac{TP+TN}{ALL}$

**Czułość (recall?)**
Jaki procent "klasy pozytywnej" rozpoznaliśmy.
Jeśli mamy 100 isntancji i 98 jest negatywnych 2 są pozytywne a powiemy ze pozytywne sa wszystkie to recall będzie będzie równy 100%. 98% probek jest zle zaklasyfikowanych, ale wszystkie probki klasy pozytywnej zostany sklasyfikowane dobrze. 
`Recall or Sensitivity measures how many of the actual positive cases were correctly identified by the model. It is important when missing a positive case (false negative) is more costly than false positives.`
$\text{recall()} = \frac{TP}{TP+FN}$
Metryka podstawowa - z niej się "składa" inne.

**Miss rate**
Odbicie recall, rzadko spotykane

**Precyzja** 
`It measures how many of the positive predictions made by the model are actually correct. It's useful when the cost of false positives is high such as in medical diagnoses where predicting a disease when it’s not present can have serious consequences.`
$\text{precision()} = \frac{TP}{TP+FP}$

**Specificity**
$\text{specificity()} = \frac{TP}{TN+FP}$

**Fallout**
Odwrotność specificity

#### Złożone meteyki
**BAC (Balanced Accuracy Score)**
Średnia arytmetyczna recall i specificity - "na to można patrzeć zawsze, czy problem jest zbalansowany czy nie".
$BAC()=\frac{\text{Recall}+\text{Specificity}}{2}$

**Gmean (Geometric Mean Score)**
Zazwyczaj jest to pierwiastek Recall i Specificity, nie powie więcej niż powie BAC.

**FB**
Średnia ahrmoniczna recall i precyzji. Beta to waga dla precyzji. Silnie krytykowana metryka przez tą dodatkowa wage, bo często liczy się B=1 i elo. Nie zawsze B=1 jest dobre.
$F_\beta=(1+\beta^2)*$...

#### Benchmark datasets
Zazwyczaj korzysta się z dostępmnych zbiorów benchmarkowych, które są wykrozystywane od lat. Żeby sprawdzić, czy algorytm jest lepszy od innego, nie chcemy tego badać na jednym zbiorze bo to mało miarodajne. Nie koncetrujemy się bardzo na jednym, konkretnym zbiorze danych, tylko na wielu różnych - różne liczby cech, różne typy cech, różne liczby próbek.

W produkcji zazwyczaj już można skupić się na o wiele węższym zakresie.

#### Dane syntetyczne
Używa się ich rzadziej bo ciężko sprawić, by one rzeczywiście coś mówiły. Wyjątkiem są dane strumieniowe. Pojawia się tam dryf koncepcji (?) sprawia, że cała przestrzeń się przesuwa, czyli nawet po nauczeniu się jakiegoś sensownego thresholdu po tygodniu może być chujowo. 

#### Trening
Sztywny podział test-trening nie jest rzetelny ani zbalansowany. O wiele lepszy jest k-Fold Cross-Validation, ale tam problem jest to, że cała klasa może zamknąć się w jednym foldzie. Rozwiązanie to Stratified k-Fold Cross Validation, gdzie podział klas w foldach odpowiada temu w oryginalnych zestawach danych. Używać zawsze - konkretnie tej powtórzonej. 

Leave-One-Out - specjalna walidacja krzyżowa. Dla małych zbiorów danych. Dla każdego splitu ilość foldów jest równa ilości próbek, gdzie tylko jeden z nich to test a wszystko inne to trening. Nie da się policzyć ani średniej ani odchylenia ani nic - na końcu jest tylko jeden wynik. Używa się tylko gdy zestawy danych są mega małe - 20, 50 próbek. Normalne metody dadzą wtedy gówniane wyniki. "Bierzemy tyle ile sie da do treningu i liczymy na to ze klasyfikator naucyz sie czegokolwiek".

K-Fold wybiera się na podstawie rozmiaru zbioru danych. Im większy zbiór tym mniejsze K. 
```
The choice of K affects the trade-off between bias and variance:
Small K (e.g., K=2 or K=5): Faster computation with increased variance in performance estimates.
Large K (e.g., K=10 or K=n, where n is the size of the dataset): Lower variance but higher computational cost. K =n corresponds to Leave-One-Out Cross Validation (LOOCV).
```

