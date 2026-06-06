## Uczenie pół-nadzorowane
Czyli część próbek ma etykiety, część nie. Problemem są dane, które niby istnieją, ale są nieotykietowane. Zakładamy, że oetykietowanie wszystkiego jest kosztowne, ale mamy chociaż kilka danych przypisanych do jakiejś klasy.

#### Uczenie aktywne
Szczególny przypadek uczenia pól-nadzorowanego, opieramy się na ekspercie człowieku, "human in the loop". Taki człowiek jest kosztowny, dlatego chcemy minimalizować wykorzystanie go. 

Mamy masę danych nieoznaczonych. Decydujemy które lądują do eksperta, które damy radę sami jakoś oznaczyć. Podobieństwo możemy określić na podstawie chociażby dystansu, ale losowy wybór też całkiem działa. Można też szukać na podstawie dystansu, **ale najbliżej granicy decyzyjnej**. Jako tako działają próbki syntetyczne. Ewentualnie można wytrenowac klasyfiktor na tym, co się ma i tyle. 

**Typowy przebieg uczenia półnadzorowanego:**
1. Na początku bardzo mało etykiet.
2. Manualnie etykietuje się część danych.
3. Model zaczyna działać - można robić mądrzejsze wybory.
4. Iteracyjnie poprawia się model wraz z napływem nowych etykiet.