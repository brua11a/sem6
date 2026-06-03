Klasyfikacja danych niezbalansowanych

Confusion matrix - służy do wyznaczenia metryk. TP, FP, FN, TN...
Accuracy - dokładność - procent poprawnych klasyfikacji. Nie działa dla danych niezbalansowanych. 
Precision - precyzja
Recall - czułość - liczba TP w stosunku do wszystkiego. Stosunek próbek klasy mniejszościowej do wszystkiego. 
Specificity - recall, ale dla klasy większościowej.
Precision - precyzja - jaki procent próbek uznanych za mniejszosciowe jest rzeczywiscie mniejszosciowych.

Accuracy, precision i recall są bazowe
Pozostałe są zagregowane, np. balanced accuracy score. Średnia z tych powyżej. G-mean to średnia geometryczna accuracy, precision i recall, w zaleznosci od wzoru są różne. F-sciore to średnia kanoniczna. 

IR - Imbalance Ratio, stopień niezbalansowania. IR=9 oznacza, że na 1 próbke klasy mniejszosciowej będzie 9 wiekszosciowej.

Estymacja miar - można to stosować zawsze, w szczególności ważne przy zbiorze niezbalansowanym. Stratyfikacja polega na tym, że zachowane są proporcje z oryginalnego zbioru danych w każdym foldzie. 

#### Podejścia
Próbkowanie - nadpróbkowanie, podpróbkowanie. Pojawia się SMOTE, Random Undersampling, Random Oversampling...

Bagging podobno byl przypomnij sobie. Wyklad 6. Dlaczego musimy coś robić jak wiemy, że dane są niezbalansowane? Bo zazwyczaj zależy nam na klasie mniejszościowej. Kanoniczne algorytmy klasyfikacji są stronnicze wobec klasy większościowej, po to są te wszystkie preprocessingi, ważenia itd. 

