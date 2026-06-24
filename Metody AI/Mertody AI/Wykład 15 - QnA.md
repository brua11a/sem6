Statyczna selekcja - klasyfikatory wbybrane na poczatku sa do konca
Dynamiczna selekcja - są w runtime wybierane
Selekcja jest wykonywana na podstawie metryk takich jak precision, BAC...
Regiony kompetencji
Metryki przy niezbalansowanych - nie wolno uzywac accuracy bo preferuje klasie wiekszosciowa. 
Recall - ile pozytywnych wykryto ze wszystkich pozytywnych
Specificity - ile negatywnych wykryto ze wszystkich negatywnych
Precision - ile pozytywnych wykryto z uznanych za pozytywne
BAC dziala git 
Stratyfikacja - zachowany balans klas względem og datasetu
Undersampling, oversampling...
Do niezbalansowanych zbiorów można też użyć zespołów. 
Można też dodać wagi.
Nienadzorowane - nie ma etykiet.
Klasteryzacja szuka podobnych sampli i je grupuje.
K-means w klasteryzacji - wybiera K punktów, przypisuje sample do najbliższego punktu, przesuwa punkty do średniej pozycji sampli, co tworzy nowy centroid. W pętli aż będzie git.
K-means++ nie losuje centoridow tylko cos???
Fuzzy c-means - próbka nie nalezy do jednej grupy.
Automatyczny dobór liczby klastrów - metoda łokcia, liczy się metryki aż nie zauważy się znaczącej poprawy. 
Klasteryzacja hierarchiczna - nie definiuje się liczby klastrów?
Self-learning - generowanie etykiet z klasteryzacji.
DeepCLuster - z przedostatniej warstwy sieci neuronowej dostaje się cechy i sie je klasteryzuje???? huh
Self learning - próbki oetykietowane maja "wzmocnic" te bez etykiet.
Self labeling, active learning
Active learning - niektóre próbki ocenia człowiek, tworzy to pewne "granice". Próbki z granicy decyzyjnej. Odległość od granicy decyzyjnej liczy się na podstawie??? Granicę samą określa się na podstawie "wsparcia" czyli próbek które są 50/50
Self labeling - nie ma człowieka. Jak działa chuj wie. Self labeling od self learningu różni się tym, że w self learningu nie mamy nic, a w labelingu mamy coś.
Danych strumieniowych nie da się zapisać, zmieniają się (dryf koncepcji), model trzeba cały czas obserwować czy się nie psuje. 
Niezbalansowanie może się zmieniać w czasie. Jeśli klasa mniejszosciowa stanei sie wiekszosciowa to precision się wywala na łeb.
Dryf realny - zmienia się granica decyzyjna, klasyfikator się psuje
Dryf wirtualny - zmienia się rozkład ale granica sie nie zmienia. Dzieje się dryf ale to nic nie zmienia.
TestThenTrain - trening na pierwszym chunku, potem test czy jest dobrze + trening jesli nie, w kolko. Szybszy, bardziej adaptacyjny, ale gubi trochę wiedzy.
Prequential - różni się tym, że chunki się nachodzą, co pozwala zachować dane. Wolniejszy, dokładniejszy. 
Trudno analizować statystycznie strumień.
Podejście do analizy strumienia - w oknach albo próbka po próbce (Online). 
Nowe problemy strumienia - nowe klasy, nowe cechy...
Stosuje się metody klasyfikacji zespołowe. 
Dane multimodalne - posiadają kilka modalnośći, np. film ma obraz, tekst i dźwięk. Zazwyczaj jednym klasyfikatorem nie da się trafnie ocenić wszystkich trzech jednocześnie. Multimodalność jest dla nas dobra bo jedną próbkę opisuje na kilka sposobów. Zróżnicowana pula. Zespoły znowu. Fuzja wczesna i późna - wczesna najpierw łączu się do jednego wektora cech. Przed tym trzeba w jakiś sposób wyekstrachować cechy, żeby złączyć modelności w jeden wektor. 
Multi-view od multi-modal - jedna modalność pod różną "perspektywą" wygląda inaczej. DLa tabeli będzie to random subspace.

jaki kurwa cwel ty