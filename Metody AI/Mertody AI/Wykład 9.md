Klasyfikacja danych niezbalansowanych

[[Wykład 4 - ten ważny]]

#### Metryki przy danych niezbalansowanych
Accuracy, precision i recall to metryki bazowe. Pozostałe są zagregowane
1. **Balanced accuracy** to średnia arytmetyczna accuracy osobno dla każdej klasy.
2. **G-mean** to średnia geometryczna accuracy, precision i recall. W zależności od definicji są różne wzory.
3. **F-score** to średnia harmoniczna z precision i recall. 

#### Inny żargon
**IR - Imbalance Ratio**, stopień niezbalansowania. IR=9 oznacza, że na 1 próbke klasy mniejszosciowej będzie 9 wiekszosciowej.

**Estymacja miar** - stratified k-fold cross validation, znane z wcześniej, można to stosować zawsze, w szczególności ważne przy zbiorze niezbalansowanym. Stratyfikacja polega na tym, że zachowane są proporcje z oryginalnego zbioru danych w każdym foldzie. 

#### Podejścia do niezbalanoswania
Zazwyczaj jest to jakieś próbkowanie lub dane syntetyczne:
- **nadpróbkowanie**, np. Random Oversampling
  >Próbki z klasy mniejszościowej są powielane
  >
  >![[Pasted image 20260606162131.png]]
- **podpróbkowanie**, np. Random Undersampling
  >Próbki z klasy większościowej są usuwane, na przykład zostają tylko centroidy - wtedy oryginalne instancje klasy większosciowej nie pozostają w datasecie.
  >
  >![[Pasted image 20260606162148.png]]
- **SMOTE** (Synthetic Minority Oversampling Technique)
  >Poprzez interpolację istniejących próbek klasy mniejszościowej, generuje się nowe.
  >
  >![[Pasted image 20260606162208.png]]

Dlaczego musimy coś robić jak wiemy, że dane są niezbalansowane? Bo zazwyczaj zależy nam na klasie mniejszościowej. Kanoniczne algorytmy klasyfikacji są stronnicze wobec klasy większościowej, po to są te wszystkie preprocessingi, ważenia itd. 

