## Po co to
Pojedynczy klasyfikator ma swoje słabe strony - może się mylić na pewnych typach danych, być wrażliwy na szum, przeuczyć się. Zamiast polegać na jednym modelu, używasz wielu i łączysz ich decyzje.

```
Ensembles are effective because they address three key challenges in machine learning:

1. Statistical Problem
When the set of possible models is too large for the available data, multiple models can fit the training data well. A learning algorithm might pick just one of them, which may not generalize well. Ensembles reduce this risk by averaging across multiple models.

2. Computational Problem
In cases where algorithms cannot efficiently find the optimal model, ensemble learning mitigates this by combining several approximate solutions.

3. Representational Problem
If the true function is not present in the set of the base learner, ensembles can combine multiple models to better approximate complex target functions.

Note: The main challenge is diversity among the models. For ensembles to be effective, each base model should make different types of errors. Even if individual models are relatively weak, the ensemble can still perform strongly if their mistakes are uncorrelated.
```

## Zespół klasyfikatorów
Są dwa główne pomysły na stworzenie grupy klasyfikatorów, tzw. *Classifier ensemble*:
- **Topologia równoległa** - bardziej popularna
- **Topologia szeregowa**

![[Pasted image 20260604203843.png]]

#### Generacja zespołu
Klasyfikatory mają być zdywersyfikowane i dokładne (nielosowe). Jeśli wszystkie klasyfikatory są identyczne, zespół nie daje żadnej przewagi - będą się mylić na tych samych próbkach. Jako "identyczne" rozumiem ten sam algorytm, te same dane, te same hiperparametry. Tworzy to dokładnie ten sam model.

1. **Dywersyfikacja na podstawie danych:**
   - **Bagging** - $n$ klasyfikatorów trenowanych na losowaniu ze zwracaniem, każdy dostaje inną próbkę obiektów i wszystkie cechy
   - **Random Subspace** - każdy model dostaje wszystkie obiekty, ale tylko część cech (bagging po kolumnach)
   - **Random Patches** - losujemy i obiekty i cechy (bagging + random subspace razem)  

![[Pasted image 20260604203928.png]]

2. **Dywersyfikacja na podstawie hiperparametrów** - np. różne wartości $k$ w KNN
3. **Dywersyfikacja na podstawie algorytmów**:
   - **Homogeniczny** - te same algorytmy
   - **Heterogeniczny** - różne algorytmy

Istnieją miary oceniające jak bardzo zespół jest zróżnicowany.

#### Selekcja (opcjonalnie)
*Overproduce and select based on local competencies*

**Claude wysryw:**
```
Selekcja rozwiązuje problem że nie każdy klasyfikator jest dobry wszędzie.
Wyobraź sobie że masz 100 klasyfikatorów. Część jest dobra na łatwych próbkach, część na trudnych, część na próbkach z klasy A, część z klasy B. Gdybyś użył wszystkich 100 do głosowania — słabe klasyfikatory "rozmywają" decyzje dobrych.
Selekcja mówi: zamiast używać wszystkich, wybierz tylko tych którzy są kompetentni dla tej konkretnej sytuacji.
Różnica między statyczną a dynamiczną:

Statyczna — wybierasz najlepszych raz dla całego zbioru testowego. Prostsza, ale nadal jeden zespół dla wszystkich próbek.
Dynamiczna — dla każdej próbki pytasz "kto jest tutaj ekspertem?" Klasyfikator świetny na próbkach podobnych do tej dostaje głos, reszta nie. Lokalny ekspert zamiast globalnego.

Analogia: statyczna to jak wybranie najlepszego lekarza ogólnie. Dynamiczna to jak wybranie specjalisty zależnie od choroby — kardiolog dla serca, neurolog dla głowy.
```

1. **Statyczna** - klasyfikatory wybiera się raz przed predykcją dla całego zbioru testowego
2. **Dynamiczna** - dla każdej próbki testowej wybierany jest nowy klasyfikator
   - **KNORA-E** (k-Nearest Oracles Eliminate) - wydzielamy zbiór walidacyjny (DSEL). Dla próbki testowej szukamy sąsiadów w DSEL (lokalny region kompetencji). Każdy klasyfikator z puli klasyfikuje tych sąsiadów. Lokalną wyrocznią zostają klasyfikatory, które poprawnie zaklasyfikowały wszystkich sąsiadów tej initial próbki.
   - **KNORA-U** (k-Nearest Oracle Union) - ponownie tworzy się DSEL i szuka sąsiadów. Bierze wszystkie klasyfikatory, które zaklasyfikowały poprawnie choć jednego sąsiada, składa je w pulę i przeprowadza ważone głosowanie (waga = liczba poprawnych klasyfikacji)
   - **DES-Clustering** - zamiast szukać sąsiadów dla każdej próbki testowej osobno, klastry są wyznaczane raz na zbiorze walidacyjnym i każdemu klastrowi przypisywany jest zespół klasyfikatorów. Próbka testowa jest przypisywana do klastra i klasyfikowana przez jego zespół.

#### Kombinacja
Chodzi o wyciągnięcie ostatecznej decyzji z pod-decyzji klasyfikatorów w zespole.

https://medium.com/@awanurrahman.cse/understanding-soft-voting-and-hard-voting-a-comparative-analysis-of-ensemble-learning-methods-db0663d2c008

1. **Hard level (na predykcjach):**
   - **Voting (weighted)** - głosowanie większościowe, można ważyć klasy/klasyfikatory/instancje
   - **Stacking** - trenujemy meta-klasyfikator na wyjściach bazowych klasyfikatorów

**Model abstrakcyjny - Wyrocznia** - klasyfikator który podaje prawdziwą odpowiedź jeśli chociaż jeden klasyfikator w zespole podał ją poprawnie. Górna granica zespołu. **Na egzamin: nie da się osiągnąć lepszego wyniku niż wyrocznia.**

2. **Soft level (na wsparciu/prawdopodobieństwach):**
   - **Sum, Mean** - uśrednianie pewności
   - **Product** - iloczyn pewności
   - **Maximum** - bierzemy najbardziej pewny klasyfikator
   - **Minimum** - wierzymy tylko tak bardzo jak najmniej pewny klasyfikator