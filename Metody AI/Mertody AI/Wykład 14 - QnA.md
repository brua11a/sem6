D1.21 chyba zaliczenie

Taksonomia - supervised, unsupervised, semi-supervised i jakie tam są zadania
Regresja vs Klasyfikacja?
AI vs ML: AI ma naśladować rozumowanie człowieka, "Machine Learning to dziedzina zajmująca się algorytmami, które automatycznie poprawiają się na podstawie danych. ML jest zwykle wąski - rozwiązuje konkretne zadanie."
Relacja między problemem a zbiorem - zbiór to próbki wysamplowane. Próbka to wektor cech. Problem to jakaś zagwostka którą chcemy rozwiązać.
Przestrzeń cech to zbiór wszystkich próbek, przesteń n-wymiarowa gdzie n to liczba cech.
Granica decyzyjna to threshold, który rozdzieli próbki należące do różnych klas. Wylicza się na podstawie regresji?
Nadzorowane - są etykiety. Nienadzorowae - nie ma, ale szukamy zaleznosci. K-means. K-means to najprostszy algorytm klasteryzacji, grupowania. Polega po prostu na dystansach. Inicjalizuje się $K$ centroidów (grup, punktów centralnych klastra), np. losowo. 
Dane tabularyczne są trudne bo są różne, niehomogeniczne.
Cechy najtrudniejsze to cechy kategoryczne, one hot encoding?? Label encoding, przypisujemy liczby do tekstu. Bianry encoding. Label encoding ma problem bo przypisuje wieksze liczby, co powoduje bias.
Klątwa wymairowości - nadmiar cech, kolumn pogarsza generalizację jakości. Cierpią na tym metody polegająće na dystansie, *dystansowe* bo ?????
Inputacja - kiedy mamy braki danych. Podejście jedno i wielo?? Średnia, mediana, moda? Jedno od wielowymiarowej rozni sie tym ze bierze sie pod uwage wiecej cech.
Normalizacja standardowa, przedziałowa, L2
Selekcja - podzbior cech. Ekstrakcja - na podsatwie satrych cech liczy sie nowa. PCA - skrot od ????
W systemie medycznym powinno się opierać na ??? bo ???? w sumie niewiadomo na czym zalezy
Czym sie rozni selekcja filtrowa od wrapperowej??
Miary teudnośći problemu - do czego sluza? nie wiadomo, w tym kontekscie a nie powie 
Metryki i miary dystansu - euklides, manhattan, minkowski... Metryka musi spełniać warunki, m.in. nierówność trójkata. Moze byc mniejsza od 1 ale nie od zera. 
Self learning - uzywa sie tam klasteryzacji do samo-uczenia i tworzenia "etykiet".
KNN to klasyfikator leniwy bo zapamiętuje tylko parametry, zapamiętuje tylko zbior treningowy. Liczy się odległosć nowego punktu do całego zestawu treningowego, sprawdza się k najbliższych sąsiadów, patrzy się na ich etykiety, przypisuje się etykietę na tego podstawie. Co można poważyć? dystans, częstość występowania, mozna losowac....
Protokoły eksperymentalne - metryki, dane, hipoteza, metodologia?? (sposób podziału danych). Metryki - recall, accuracy, precision, BAC, F1 score, specificity, (miss rate, fallout). Recall - ile poprawnych z poprawnych jest actually poprawnych. Po prostu zjarzyj do wykladu 4.
Jeśli nie wiem nic to używam BAC bo jest uniwersalny. 
Protokoły eksperymentale w zaleznosci od danych - train test split, repeated stratified k-fold. Stratyfikacja jest wazna bo lepiej oddaje OG zbior i unika sytuacji w ktorejw szystkie instancje kalsy są w jendym foldzie. Walidacja jeszcze z powtorzeniami zadziała tak samo, ale calosc bedzie robiona kilka razy.
(TAMTO JAKO PIERWSZE PYTANIE CHYBA?)
Leave one out. Liczba próbek jest równa liczbie foldów. Używa sie gdy danych jest mało. Im wiecej mamy probek tym mniej potrzebuejmy foldów bo mamy wieksza pewnosc, ze kazdy fold pozwoli zgeneralizować wiedzę i odda proporcję między foldami? Niby to nie wystarczy.
Leave one out ma problem ze statystyką - nie ma na czym ich liczyć.
Holdout??? Metryki na pewno będą?? Holdout polega na "odłożęniu" danych na koniec cokolwiek to znaczy. Mam zbior treningowy, walidacyjny i holdout. Nie slyszalem pytania. Jeszcze bardziej nie slysze odpwoiedzi. Jeśli mamy tyljo 1 hokdout to nie wiadomo czy jest dobrze?
Ostatnie pytanie bedzie turbo otwarte i mamy się mądrzyć.

Będą 4 pytania na 1 stronie, jest miejsce na odpowiedz. Miejsce spoza przeznaczonego pola sie nie liczą. Brudnopis z tylu kartki. 

Miary, protokoły (2). Pierwsze pytanie trzeba dobrze, jak jest zle to gwalt i kastracja. Reszta jest na "połówki". Sensitivity!!!!!!!!!

Analiza statystyczna - robi sie po to, by stwierdzić czy jedna metoda jest lepsza od innej. Przyjmujemy 5% szansy na błąd. Normalnośc sprawdza sie shapiro wilkiem. Jak jest to t-student, jak nie to 5x2. Najlepszy jest F-test dla powtorzonej RSKF 5x2??
2 klasyfikatory wiele zbiroow - signed rank Wilcoxon. 
Wiele klasyfikatorow wiele zbiorow - Friedmann po czym Nemenyi???
Jak mam wiele zbiorow i wiele klasyfikatorow to wilcoxonem sprawdza sie nie same foldy tylko średnie dla zbiorów. 
Generacja w zespole służy do stworzenia zdywersyfykowanej grupy klasyfikatorów. Robimy to żeby każdy był "specjalistą" od swojego problemu. Gdyby były takie same to po co zespol. Poza dywersyfikacją musi być jeszcze dokładność (wysoka precyzja), czyli mają być lepsze od losowego. 
Bagging - każdy pod-klasyfikator będzie miał subset z oryginalnego podzbioru. Rozmiar podzbiorów jest arbitrarny. Random subspace - wybrane cechy. Jeśli nie wiemy jak duze maja byc podprzestrzenie, to wrzuca sie pierwiastek z liczby cech?? Random patches to to i to jedncozesnie.
Topologia szeregowa - pierwszy klasyfikator robi odrzucanie "z grubsza", kolejne cięższe robią bardziej granularną klasyfikację aż osiągniemy zadowalający nas wynik.
Kombinacja twarda i miękka - miękka jest na prawdopdoobienstwach, twarda jest na predykcji. Głosowanie ważone - po klasach, klasyfikatorach i instancjach. W miękkich będą średnie, maximum, minimum, najbardziej typowe to po ???? nie powie :)
Miękkie maksimum? Wybjeramy najpewniejszy klasyfikator i tyle.
Jak działą selekcja dynamiczna a statyczna? przeczytaj z wykładu 6
Kombinacja dwuetapowa - moze powie??? Głosuje się raz, po czym drugi chyba
kys niggers