UWAGA: dla kasyfikatorów, gdzie jest wiele zbiorów i wiele klasyfikatorów używa się wilcoxona signed.

### Data stream
Mamy potencjalnie nieskocznczona ilosc danychw  czasie, nie "stoją" w bazie, jsonie czy cos, bo nie mamy pelnego zbioru danych. Nie przechowuje się strumienia (teoretycznie nieskocznone capacity). Często czas podjęcia decyzji, predykcji, testu ma duze znaczenie. Na strumieniu nie zrobi sie analizy staystycznej, walidacji krzyzowej, nic nie dziala. Zmiany w strumieniu to dryf koncepcyjny. Nie polega on na tym, ze zmienia sie charakterystyka problemu (?).

W dryfie nagłym zmiana jest w jednym/krótkim punkcie czasu. Po zmianie, wczesniej wyuczony klasyfikator bylby juz losowy, malo uzyteczny.

Gradualny i inkrementalny dryf są podobne, nie dzieje się nagle tylko jest rozciąniety. W inkrementalnym w każdym kroku zmienia się rozkład, przechodi się płynnie małymi zmianami z jednego rozkłądu do drugiego. W gradualnym istnieją dwa rozkłady/koncepcje jednocześnie i do nich dążą chunki, zmieniają się proporcje. Nie rozumiem praktycznych implikacji tego.

Static imbalance, dynamic imbalance - idk

Na danych strumieniowych ofc nie da sie startyfikacji k-foldowej. RObi sie zamist tego TestThenTrain. Pierwszy wsad służy do trenowania, kolejne "porcje" są najpierw predykowane, potem służą do treningu. Zeby wyliczyć metrykę, potrzebna jest predykcja i rzeczywistość - problem jest taki, że w strumieniu dane mogą być nieoetykietowane lub mogą przychodzić z opóźnieniem, moze byc przydatny human in the loop i nie ma to sensu. Aktualizację, nowy trening nie wymagane są może zawsze? Poprzez metody statystyczne można np. wykryc ze cos jest nie tak i wtedy "dotrenować".

TestThenTrain, obok niego jest Prequential, w którym zachowujemy część kontekstu z poprzedniego data stream. Wadą jest czas przetwarzania, dużo wolniejszy. Zaletą jest większa czułość, zależy od rozmiaru okna. Jak częściej dokonujemy ewaluacji, szybciej wykryjemy dryf. Najczęściej w takich strumieniach stosuje się klasyfikatory, które pozwalają się "douczyć". Sieci neuronowe gdy się je doucza to zapomina stare dane - jest to tutaj dobre bo strumień i tak idzie tylko do przodu, strumień sprzed dryfu nas nie obchodzi za bardzo. Zdecydowana wiekszosc metod sstrumieniowych to metody zespołowe (? https://pl.wikipedia.org/wiki/Uczenie_zespo%C5%82owe).

Zespoły są łatwe do douczenia bo?? Jak może działać zespół klasyfikatorów w TestThenTrain? Na pierwszym wsadzie uczy sie (ale chuj wie co), powstaje klasyfikator. Na drugim wsadzie jest testowany tym klasyfikatorem, trenuje się drugi klasyfikator. Na trzecim chunku testuje się wszystkimi klasyfikatorami poprzez głosowanie/fuzję (?) i trenuje (znowu chuj wie co). 

Inny pomysl - gorna granica liczby klasyfikatorow. Gdy dotrzeby do granicy, najslabszy/najstarszy się usuwa. Bagging wazny przypomnij sobie.

