Uczenie nienadzorowane. Zadania w nadzorowanym - klasyfikacja i regresja. W nadzorowanym - klasteryzacja, redukcja wymiarów i estymacja gęstości rozkładu (mniej ważne). K-means to najprostszy algorytm klasteryzacji, grupowania. Nie ma etykiet, "klas", mamy punkty w przestrzeni i chcemy je pogrupować tak, żeby podobne punkty byyly w tych samych grupach. K-means polega po prostu na dystansach. Mamy k centroidów (grup, punktów centralnych klastra). Liczy się X iteracji albo do osiągnięcia oczekiwanej odleglosci. Każda instancja mierzy się odleglosc od cntroidu, przypisuje się grupę, w kółko ustala się nową centroidę o nowym polozeniu.

Klasyfikacja wieloetykietowa oznacza, że jeden obiekt będzie miał kilka etykiet. Pojawia się cos podobnego w uczeniu nienadzorowanych, fuzzy c-means. 

Automatyczny dobór liczby klastrów będzie polegał na chuj wie czym bo zyblewski edgeuje 5min zamiast uczyc. Dobrze jest wiecej klastrów niz grup, bo czasem w roznych miejscach na wykresie moga byc ta sama klasa. Zakladamy ze klasteryzacja jest dobra na podstawie ???? znowu edguje

Zazwyczaj zbiory ktore sie klastruje mają etykiety. Zaklada sie z enie ma ich w treningu ale sluza do weryfikacji.

Klasteryzacja hierarchiczna (agglomeratywna??) polega na tym ze sie robi drzewo, te metody działają albo na instancji w klastrze po czym sie laczy lub na odwrot wszyskto zaczyna w jendym klastrze po czym sie dzieli???

Metryki - podajemy 2 ale jest w chuj. Pierwsza to silhouette coefficient. Sprawdza średnie dystanse od próbki do próbek z tej samej klasy. Jest problematyczny jeśli klastry się na siebie nachodzą. Zakres od -1 do 1. Drugi nwm jaki nie uslyszalem jebac.

Purity, completness, homogenity. Nie wyjasnil co to ale bylo na slajdzie. 

Self learning poelga na tym ze uczy sie np. kalsyfikator ale nie mamy etykiet wcale ale trzeba to wyuczyc spsoob jest kilka nie wchodzi w to bo po chuj pokazemy metode oparta na k-means. Jest bardzo rposta poelga na tymz  ejak mamay sie ckonwolucyjna jest konwolucja pooling itd my w pewnym momencie przed kalsyfikatorem przed ostatania warstaw ktora moze byc np. 1 regresja logistycznya jest jakas reprezentacja tabulacyrcza wyekrstaktowana warstwa decyzyjna klasyfikuje ejdynie te reprezentacje. Problmem poelg ant ym ze zeby polcizyc miec chuj wie co trzeba mie cetykiety. Mozna zmaiast tego skalstrowc zaklada sie zze ma sie X grup X klastrow w kazdej epice uczenia nasza prezestrzen ktora wchodzi do klasyfikatora klastruje sei na np 5 grup dla 5 klas i te klastry są etykietami na tym sie cuyz siec liczy strate robi rpopagacje wsteczna.

