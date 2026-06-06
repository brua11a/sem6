#### AI vs ML
Model to algorytm, który zgeneralizował wiedzę. Model jest algorytmem. Zazwyczaj mowa o czymś, co zostało już stworzone, gotowe, nauczone i służy do podejmowania decyzji. 

```
A machine learning model is, fundamentally, a parameterized function f(x; θ), where x represents input data and θ represents the model’s parameters. During training, the ML algorithm optimizes the parameters θ such that f(x; θ) accurately approximates the underlying function that maps inputs to outputs. In essence, the model encapsulates the knowledge gleaned from the training data.
```

Machine Learning to dziedzina zajmująca się algorytmami, które automatycznie poprawiają się na podstawie danych. ML jest zwykle wąski - rozwiązuje konkretne zadanie.

AI historycznie obejmowało m.in. systemy eksperckie (ręcznie pisane reguły `if/else`), dziś najczęściej oznacza właśnie ML. Termin "AI" sugeruje bardziej ogólne, ludzkie rozumowanie - w praktyce to jednak wciąż ML wyspecjalizowany w danym obszarze.

#### Czym jest problem
W sumie cokolwiek - np. klasyfikacja: "czy to kot czy pies, czy on ma raka". Poza problemem są potrzebne zbiory danych - wszystkie uporządkowane informacje, do których mamy dostęp, reprezentacja problemu. Wzorzec (sample) to pojedynczy obiekt z tej bazy danych, opisany przez cechy, czyli jego mierzalne właściwości.

#### Co to taksonomia
"A system for naming and organizing things, especially plants and animals, into groups that share similar qualities".

**W taksonomii ML jest:**
1. Unsupervised Learning (Clustering, Dimensionality Reduction, Denstity estimation)
2. Supervised Learning (Classification, Regression)
3. (ewentualnie) Semi-supervised Learning - Reinforcement Learning do tego nie należy pomimo tego co piszą na Internecie.

#### Uczenie
**Indukcyjne** - uczenie przez doświadczenie. "Any hypothesis found to approximate the target function will over a sufficielnty large set of training examples will also approximate the target function well over other unobserved examples". Czyli jak nauczy się na przykładach to powinno poprawnie przybliżać podobne przykłady. 

**Supervised Learning** - nadzorowane, poprzez etykiety. Dane są oetykietowane i na nich model się uczy. Służy do generalizacji wiedzy. Instancja jest przypisywany do klasy (`kot`, `pies`, `0`, `1`) lub do wartości. Liczymy na to, że dzięki generalizacji będzie możliwa klasyfikacja kolejnych przykładów po nauczeniu - samplom zostanie przypisana odpowiednia ze znanych etykiet.
**Regresja** - etykietą jest wartość ciągła, na przykład `21.5C`. "Przewiduję temperaturę na podstawie kilku poprzednich dni zamiast decydować zimno/ciepło".

**Uczenie nienadzorowane, Unsupervised** - nie ma etykiet, dane są analizowane w celu zrozumienia ich struktury oraz zależności między samplami. Instancję są grupowane wraz z tymi "podobnymi" do siebie.