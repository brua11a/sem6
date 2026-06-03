#### AI vs ML
Model to algorytm, który zgeneralizował wiedzę. Model jest algorytmem. Zazwyczaj mowa o czymś, co zostało już stworzone, gotowe, nauczone i służy do podejmowania decyzji. 

Machine learning to nauka o algorytmach komputerowych, które automatycznie się poprawiają wraz z doświadczeniem. W 99% przypadków jak mówią o AI to jest to po prostu ML - *system ekspercki*, drzewo decyzyjne oparte na `if` statementach. ML często służy do konkretnego zadania, zaś AI do "ogólnych" zadań - rozumowanie podobne do ludzkiego. 

#### Czym jest problem
W sumie cokolwiek - "czy to kot czy pies, czy on ma raka". Poza problemem są potrzebne zbiory danych - wszystkie uporządkowane informacje, do których mamy dostęp, reprezentacja problemu. Wzorzec (sample) to pojedynczy obiekt z bazy danych. 

#### Co to taksonomia
"A system for naming and organizing things, especially plants and animals, into groups that share similar qualities". W taksonomii ML jest Unsupervised Learning (Clustering, Dimensionality Reduction, Denstity estimation) i Supervised Learning (Classification, Regression), ewentualnie Semi-supervised Learning - Reinforcement Learning do tego nie należy pomimo tego co piszą na Internecie.

#### Uczenie
Indukcyjne - przez doświadczenie. "Any hypothesis found to approximate the target function will over a sufficielnty large set of training examples will also approximate the target function well over other unobserved examples". Supervised - nadzorowane, poprzez etykiety, służy do generalizacji wiedzy. Instancja jest przypisywany do klasy lub do wartości. Liczymy na to, że dzięki generalizacji będzie możliwa klasyfikacja kolejnych przykładów po nauczeniu. Regresja - etykietą jest wartość ciągła, "przewiduję temperaturę na podstawie kilku poprzednich dni zamiast decydować zimno/ciepło". Uczenie nienadzorowane, unsupervised - nie ma etykiet, dane są analizowane w celu zrozumienia ich struktury oraz zależności między samplami. Instancję są grupowane wraz z tymi "podobnymi" do siebie.

