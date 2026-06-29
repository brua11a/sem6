Kolejne wykłady to już Q&A.

Do strumieni bo sobie przypomniał: analiza statystyczna i dodatkowe trudności.
Nie zrobi się analizy statystycznej w klasyczny sposób, bo strumień się nie kończy. Można zamiast tego do jakiegoś okna zbierać określoną ilość chunków po czym policzyć staystyki. Do testu statystycznego. Zbieramy accuracy z kazdego TestThanThain potem z każdego test statystyczny, wyniki z każdego okna. Pomysł jest dobry, nieidealny, często testy statystyczne nie mają sensu.

Dane syntetyczne są fajne do badań bo są przewidywalne. Daje nam ona to, że możemy przetestować jak metoda działa dla konkretnego rodzaju dryfu, na różnych oknach, różnych typów dryfów. Zazwyczaj robi się tak, ze generuje się 10 syntentcznych strumieni takich samych ale innych i sie bierze z tego srednia. Gubi sie zaleznosc na dlugosci calego strumienia. 

Na rzeczywistym strumieniu się nie analizuje statystycznie bo za bardzo nie ma jak.

Dodatkowe trudności - pojawienie się nowej klasy, zniknięcie starej klasy, pojawiają i znikają się cechy. 

___

Multimodal & multi-view data.

Dane multimodalne - różnych typów, np. video i głos. Obraz, tekst, dźwięk, tabele. Najbardziej multimodalne jest video - obraz, dźwięk i tekst. Chcemy to rozdzielać, żeby skonstruować zespół - jest to część generacji i różnorodności. Wiele modalności (przestrzeni cech) pozwala na ekstrakcję komplementarnych informacji - zespoły klasyfikatorów i różnorodność. Jakaś klasa może być łatwiejsza do poznania po video, jakaś po tekście, jakaś po dźwięku itd.

Fuzja może tu polegać na zespołach z głosowaniem. Może też polegać na konkatenacji przestrzeni do jednej i wykorzystaniu jednego klasyfikatora. "Dane multimodalne są wtedy, jak dane pochodzą z różnych sensorów i nie da się ich złączyć do jednej reprezentacji bez wykonania ekstrakcji". Przed konkatenacją trzeba znormalizować wartości, bo te o mniejszym rzędzie "zginą".

Fuzja Mid, Early i Późna - doczytaj w domu bo idk, podobno nie ma konsensusu.

Problemy w kwestii multimodalności
- wysoka wymiarowość i konflikt danych, a także złożoność obliczeniowa
- dostępność danych
- przetwarzanie w czasie rzeczywistym i skalowalność

Multi-view
Patrzymy na jeden obiekt z różnych rzutów i inaczej wygląda. Liczymy na to, że dadzą nam one dodatkowe informacje. Przykładem będzie branie tylko konkretnych kolumn z tabeli. 

