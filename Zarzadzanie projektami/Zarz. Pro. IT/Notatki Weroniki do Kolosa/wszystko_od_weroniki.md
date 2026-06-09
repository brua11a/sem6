KOMPLEKSOWE KOMPENDIUM WIEDZY: ZARZĄDZANIE PROJEKTAMI IT
MODUŁ 1: FUNDAMENTY I INICJOWANIE PROJEKTU

1. Definicja projektu i zarządzania projektami
	• Projekt (wg PMBOK v.7): Tymczasowe przedsięwzięcie podejmowane w celu stworzenia unikalnego produktu, usługi lub rezultatu.
	• Projekt (wg PMBOK v.8): Tymczasowe przedsięwzięcie realizowane w celu wytworzenia wartości poprzez unikalne rezultaty (A temporary endeavor undertaken to create value through unique outcomes).
	• Kluczowe cechy projektu:
		○ Tymczasowość: ma jasno określony początek i koniec.
		○ Unikalność: rezultat różni się w pewnym stopniu od wszystkich podobnych produktów/usług.
		○ Złożoność: łączenie elementów różnego typu.
		○ Ograniczenia: określony czas, koszt i zakres.
		○ Wartość: każdy projekt musi dostarczać określoną wartość biznesową lub użytkową.
	• Zarządzanie projektami: Zastosowanie wiedzy, umiejętności, narzędzi i technik do działań projektowych w celu dostarczenia wartości i osiągnięcia zamierzonych rezultatów.

2. Klasyfikacja projektów
	• Według pochodzenia zlecenia: wewnętrzne vs. zewnętrzne.
	• Według orientacji: procesowo vs. obiektowo.
	• Według stopnia nowości: o niskim vs. o wysokim stopniu nowości.
	• Według rozmiaru: małe, duże, wielkie.

3. Trójkąt Ograniczeń Projektowych (Triple Constraint)
Klasyczny model zarządzania projektami zakłada, że projekt jest ograniczany przez trzy ściśle powiązane czynniki. Zmiana jednego z nich bezpośrednio wpływa na pozostałe:
	1. Zakres (Scope): Co ma zostać zrobione? Jakie funkcje i cechy ma posiadać produkt?
	2. Czas (Time): Ile czasu mamy na realizację? Jakie są terminy i kamienie milowe?
	3. Koszt/Budżet (Cost): Jakie środki finansowe i zasoby są dostępne?
W nowszych podejściach w centrum trójkąta (lub jako dodatkowy wymiar) stawia się Jakość oraz dostarczaną Wartość.

4. Cykl życia projektu (Tradycyjny)
Składa się z 4 głównych faz, z których każda odpowiada na inne wyzwania:
	1. Faza definiowania (Inicjowanie): Wybór właściwego projektu, sformułowanie koncepcji, powołanie kierownika projektu.
	2. Faza przygotowania (Planowanie): Określenie warunków skutecznej realizacji, dekompozycja zadań, harmonogramowanie, budżetowanie.
	3. Faza wykonawstwa (Realizacja i Kontrola): Skuteczna realizacja zadań, monitorowanie postępów, zarządzanie odchyleniami i zmianami.
	4. Faza zakończenia (Zamknięcie): Wdrożenie rezultatów projektu, odbiory formalne, rozliczenie budżetu, wyciągnięcie wniosków na przyszłość (Lessons Learned).

5. Interesariusze projektu (Stakeholders)
Osoby, grupy lub organizacje, które mogą wpłynąć na projekt lub na które projekt ma wpływ.
	• Podziały interesariuszy:
		○ Wewnętrzni (np. sponsor, kierownik projektu, zespół, rada nadzorcza) vs. Zewnętrzni (np. klient, podwykonawcy, użytkownicy końcowi, urzędy regulacyjne).
		○ Kluczowi (duży wpływ/silne dotknięcie projektem, np. sponsor, główny klient) vs. Drugorzędni (ograniczony wpływ, np. media).
		○ Pierwotni (bezpośrednio korzystają z efektów, np. użytkownicy systemu) vs. Wtórni (pośrednio powiązani, np. lokalne sklepy przy remoncie drogi).
		○ Pozytywni (wspierają projekt) vs. Neutralni vs. Negatywni (mogą blokować lub krytykować projekt).

MODUŁ 2: ZAKRES PROJEKTU I ZBIERANIE WYMAGAŃ

1. Pułapki w komunikacji z klientem i sposoby radzenia sobie z nimi
Podczas definiowania zakresu IT, wypowiedzi klientów bywają subiektywne i nieostre. Student/PM musi potrafić je sprecyzować:
	• „To ma być intuicyjne” $\rightarrow$ Pułapka: Skrajnie subiektywne pojęcie. Rozwiązanie: Poprosić o kryteria akceptacji. Zapytać: „Jaką konkretną czynność użytkownik musi wykonać bez instrukcji?”.
	• „Zróbcie to jak w aplikacji X” $\rightarrow$ Pułapka: Skrót myślowy, nieuwzględniający różnic w procesach biznesowych klienta. Rozwiązanie: Zapytać o cel: „Jaki konkretny problem rozwiązujemy tym rozwiązaniem?” oraz „Kto dokładnie jest użytkownikiem?”.
	• „Jeszcze zobaczymy / Dogadamy się później” $\rightarrow$ Pułapka: Prosta droga do pełzania zakresu (Scope Creep). Rozwiązanie: Wyjaśnić, że dekompozycja pracy i formalny zapis są konieczne, by wyestymować czas i budżet.
	• „To ma działać szybko” $\rightarrow$ Pułapka: Nieweryfikowalne. Rozwiązanie: Ustalić mierzalne parametry niefunkcjonalne (np. „Czas ładowania strony głównej przy 1000 jednoczesnych użytkownikach nie może przekroczyć 1,5 sekundy”).

2. MVP – Minimum Viable Product (Minimalnie Satysfakcjonujący Produkt)
W podejściu zwinnym i Lean Startup kluczowe jest jak najszybsze dostarczenie wartości i zebranie informacji zwrotnej.
	• Minimum: Wersja okrojona, zawierająca tylko kluczowe funkcje (esencja pomysłu), wymagająca najmniejszego nakładu pracy.
	• Viable (Wykonalny/Żywotny): Działający, stabilny produkt, który realnie dostarcza wartość i rozwiązuje podstawowy problem użytkownika.
	• Feedback: Głównym celem MVP jest zebranie realnych opinii od użytkowników, aby uniknąć budowania produktu, którego nikt nie chce.

MODUŁ 3: TRADYCYJNE PLANOWANIE (CZAS, HARMONOGRAM, ZASOBY)

1. Struktura Podziału Prac (WBS – Work Breakdown Structure)
	• Graficzna lub hierarchiczna dekompozycja całości zakresu prac projektu na mniejsze, łatwiej zarządzalne elementy (pakiety prac – Work Packages).
	• Zasada 100%: WBS obejmuje 100% prac zdefiniowanych w zakresie projektu i uwzględnia wszystkie produkty cząstkowe (zarówno techniczne, jak i zarządcze). Nic spoza WBS nie może być realizowane w projekcie.

2. Szacowanie czasu i Metoda Ścieżki Krytycznej (CPM)
	• Ścieżka Krytyczna (Critical Path): Najdłuższy ciąg zadań zależnych w projekcie. Wyznacza minimalny całkowity czas trwania projektu. Każde opóźnienie zadania na ścieżce krytycznej opóźnia cały projekt.
	• Rezerwa całkowita (Total Float / Total Slack - TB): Czas, o jaki można opóźnić rozpoczęcie lub wydłużyć trwanie danego zadania bez wpływu na planowaną datę zakończenia całego projektu. Zadania na ścieżce krytycznej mają rezerwę całkowitą równą 0 (TB = 0).

3. Optymalizacja i kompresja harmonogramu
Gdy planowany czas realizacji przekracza wymagany termin, stosuje się techniki kompresji:
	• Crashing (Intensyfikacja działań): Skracanie czasu trwania zadań poprzez dodawanie zasobów (np. nadgodziny, dodatkowi ludzie). Skutek: Zazwyczaj drastycznie zwiększa koszty i ryzyko.
	• Fast Tracking (Szybka ścieżka): Równoległe wykonywanie zadań, które normalnie byłyby realizowane sekwencyjnie (jedno po drugim). Skutek: Zwiększa ryzyko błędów i konieczności poprawek (rework).
	• Metoda Łańcucha Krytycznego (CCM – Critical Chain Method): Planowanie z uwzględnieniem ograniczeń zasobów (nie tylko zależności technologicznych). Polega na usunięciu indywidualnych rezerw czasowych z zadań i przeniesieniu ich na koniec projektu w postaci jednego wspólnego bufora projektu oraz mniejszych buforów pomocniczych (zasilających). Sterowanie odbywa się przez monitorowanie zużycia bufora.

4. Rodzaje zasobów w projekcie
Zasoby dzielimy na kategorie, podkategorie oraz dostępność (wewnętrzne/zewnętrzne):
	1. Zasoby rzeczowe:
		○ materialne: budynki, pomieszczenia, maszyny, serwery (własne lub wynajęte).
		○ materiałowe: zużywalne materiały potrzebne do realizacji.
		○ niematerialne: patenty, prawa autorskie, licencje oprogramowania, nabyte usługi zewnętrzne.
	2. Zasoby ludzkie: Pracownicy organizacji (wewnętrzni), eksperci, konsultanci, freelancerzy (zewnętrzni).
	3. Zasoby finansowe: Gotówka, lokaty (wewnętrzne), kredyty, dotacje, wpłaty sponsorów (zewnętrzne).

MODUŁ 4: PODJĘCIA ADAPTACYJNE I ZWINNE (AGILE)

1. Narodziny Agile (2001 r.)
Frustracja tradycyjnymi metodami (tzw. Waterfall/kaskadowym), gdzie wielkie planowanie z góry kończyło się odrzuceniem oprogramowania przez rynek, doprowadziła do spotkania 17 inżynierów w 2001 r. i sformułowania Manifestu Agile. Podejście to jest klientocentryczne i zakłada elastyczne dostosowywanie się do zmian na bazie ciągłego feedbacku.

2. Porównanie podejść: Tradycyjne vs. Adaptacyjne (Zwinne)
	• Tradycyjne (PMI/PMBOK, PRINCE2, IPMA):
		○ Myśl przewodnia: Projekt da się z góry dokładnie zaplanować (Inicjacja $\rightarrow$ Planowanie $\rightarrow$ Realizacja $\rightarrow$ Kontrola $\rightarrow$ Zamknięcie).
		○ Cel: Dostarczyć dokładnie to, co zaplanowano w określonym czasie, budżecie i zakresie.
		○ Słownictwo: Plan, struktura, harmonogram, kontrola, kamień milowy, ryzyko.
	• Adaptacyjne (Scrum, Kanban, Scrumban, Design Thinking, Lean Startup):
		○ Myśl przewodnia: Projekt zmienia się w trakcie trwania, dlatego trzeba działać iteracyjnie, elastycznie dopasowując się do informacji zwrotnej.
		○ Cel: Jak najszybciej i jak najlepiej dostarczyć realną wartość dopasowaną do użytkownika.
		○ Słownictwo: Przyrost, iteracja, sprint, backlog, adaptacja, user story, przepływ.

MODUŁ 5: METODYKA SCRUM
Scrum to ramy postępowania (framework), w których ludzie mogą podjąć złożone problemy adaptacyjne, by w sposób produktywny i kreatywny dostarczyć produkty o najwyższej możliwej wartości.

1. Role w Scrumie
	• Właściciel Produktu (Product Owner): Odpowiada za maksymalizację wartości produktu oraz zarządzanie Rejestrem Produktu (Product Backlog). Jest głosem klienta/interesariuszy.
	• Scrum Master: Odpowiada za promowanie i wspieranie Scruma. Lider służebny (servant leader), który pomaga zespołowi usuwać przeszkody (bloki) i dba o efektywność procesów.
	• Zespół Deweloperski (Developers): Interdyscyplinarny, samoorganizujący się zespół (zazwyczaj 3-9 osób) posiadający wszelkie umiejętności niezbędne do stworzenia gotowego przyrostu produktu w każdym sprincie.

2. Artefakty Scruma
	• Rejestr Produktu (Product Backlog): Ewoluująca, uporządkowana lista wszystkiego, co może być potrzebne w produkcie. Jedyne źródło wymagań.
	• Rejestr Sprintu (Sprint Backlog): Zestaw elementów z Product Backlogu wybranych do bieżącego Sprintu, powiększony o plan dostarczenia przyrostu i realizację Celu Sprintu.
	• Przyrost (Increment): Suma wszystkich elementów Product Backlogu zrealizowanych podczas danego Sprintu oraz wartość przyrostów zrealizowanych w poprzednich sprintach. Musi być zdatny do wdrożenia (Done).

3. Wydarzenia (Ceremonie) Scruma
Wszystkie wydarzenia mają określony maksymalny czas trwania (Timebox). Założeniem jest stała długość Sprintu (do 1 miesiąca, najczęściej 2 tygodnie).
	• Planowanie Sprintu (Sprint Planning): Do 8h na miesięczny sprint. Ustalenie Celu Sprintu oraz wybór zadań do Sprint Backlogu.
	• Codzienny Scrum (Daily Scrum): Maksymalnie 15 minut każdego dnia. Służy synchronizacji działań zespołu deweloperskiego i zaplanowaniu pracy na najbliższe 24 godziny.
	• Przegląd Sprintu (Sprint Review): Do 4h. Spotkanie na koniec Sprintu z interesariuszami w celu podsumowania wykonanej pracy, prezentacji przyrostu i zebrania feedbacku.
	• Retrospektywa Sprintu (Sprint Retrospective): Do 3h. Spotkanie zespołu w celu przeanalizowania jak przebiegała praca i zaplanowania usprawnień procesu, narzędzi i relacji ludzkich na kolejny sprint.

4. Techniki uzupełniające (Praktyka zespołów IT)
	• User Story (Opowieści Użytkownika): Technika zapisu wymagań z perspektywy użytkownika końcowego. Szablon: Jako [rola], chcę [funkcja], aby [korzyść].
	• Estymacja i Story Points: Szacowanie relatywnej pracochłonności zadań (często za pomocą Ciągu Fibonacciego lub rozmiarów T-shirtów podczas tzw. Planning Poker), zamiast sztywnego szacowania w godzinach.
	• Velocity (Prędkość zespołu): Średnia liczba Story Points, jaką zespół jest w stanie dostarczyć w trakcie jednego Sprintu (miara historyczna, pomocna przy planowaniu).
	• Capacity (Moce przerobowe): Rzeczywista dostępność czasu członków zespołu w nadchodzącym sprincie (uwzględnia urlopy, święta).

MODUŁ 6: METODYKA KANBAN
Kanban skupia się na wizualizacji pracy, ograniczaniu pracy w toku oraz ciągłym doskonaleniu przepływu (ciągły proces, brak sztywnych sprintów).

1. Główne zasady Kanban
	• Wizualizacja pracy: Praca jest dzielona na mniejsze zadania i reprezentowana przez karty na tablicy Kanban (podział na kolumny np. Do zrobienia, W toku, Testowanie, Zrobione).
	• Ograniczenie pracy w toku (WIP Limits – Work in Progress): Wprowadzenie maksymalnej liczby zadań, które mogą jednocześnie znajdować się na danym etapie (kolumnie).
	• Zarządzanie przepływem (Flow): Monitorowanie i optymalizacja płynności przechodzenia zadań przez tablicę.
	• Zasada: „Zacznij kończyć, przestań zaczynać”: Zespół skupia się na domykaniu otwartych zadań przed pobraniem nowych z backlogu. Zaleca się patrzenie na tablicę od prawej do lewej – ułatwia to identyfikację zadań najbliższych ukończenia, w których można pomóc kolegom.

2. Korzyści z limitowania WIP
	• Redukcja czasu potrzebnego na realizację pojedynczych zadań.
	• Poprawa jakości (mniej przełączania kontekstu i mniejsze ryzyko błędów).
	• Identyfikacja wąskich gardeł (bottlenecks) w procesie.
	• Poprawa ogólnego przepływu wartości.

3. Kluczowe wskaźniki w Kanbanie
	• Czas dostarczenia (Lead Time): Całkowity czas, jaki upływa od momentu zgłoszenia/zamówienia zadania przez klienta do jego ostatecznego zakończenia i dostarczenia wartości.
	• Czas cyklu (Cycle Time): Czas, który upływa od momentu faktycznego rozpoczęcia pracy nad zadaniem (wejścia do kolumny "W toku") do jego zakończenia. Informuje o szybkości realizacji pracy.
	• Przepustowość (Throughput): Liczba zadań zakończonych w określonej jednostce czasu (np. tygodniowo). Pokazuje aktualną wydajność i produktywność zespołu.

4. Porównanie: Scrum vs. Kanban
Cecha	Scrum	Kanban
Podejście do czasu	Sprinty (stałe okienka czasowe)	Przepływ ciągły
Zmiany w trakcie	Stały zakres i cel sprintu	Dynamiczne dodawanie/zmiana zadań
Kluczowe miary	Velocity (Prędkość)	Lead Time, Cycle Time, Throughput
Główne ograniczenie	Zobowiązanie na zakres Sprintu	Limity WIP (Pracy w Toku)
Główne zastosowanie	Zespoły produktowe, rozwój nowych funkcji	Support, utrzymanie systemów, operacje

MODUŁ 7: STANDARDY I METODYKI GLOBALNE (PRINCE2 & PMI)

1. Metodyka PRINCE2 (PRojects IN Controlled Environments)
Brytyjska, ustrukturyzowana metodyka zarządzania projektami, oparta na procesach. Składa się z 5 zintegrowanych elementów (w najnowszych edycjach nacisk kładzie się na ludzi, praktyki oraz dopasowanie do kontekstu).
	• Pryncypia PRINCE2 (Zasady przewodnie) – musi ich być 7, aby projekt był uznany za PRINCE2:
		1. Ciągła zasadność biznesowa: Projekt musi mieć uzasadnienie ekonomiczne (Business Case) od początku do końca. Jeśli przestaje być opłacalny, należy go zamknąć.
		2. Korzystanie z doświadczeń: Zespół uczy się na błędach i sukcesach poprzednich projektów (Lessons Learned).
		3. Definiowanie ról i obowiązków: Każdy musi dokładnie wiedzieć, za co odpowiada (Struktura: Komitet Sterujący, Kierownik Projektu, Kierownicy Zespołów).
		4. Zarządzanie etapami: Projekt jest dzielony na co najmniej dwa etapy zarządcze (planowanie, wykonanie). Przejście do kolejnego etapu wymaga decyzji Komitetu Sterującego.
		5. Zarządzanie przez wyjątki: Kierownik Projektu ma określone tolerancje (np. $+/- 5\%$ budżetu lub czasu). Dopóki się w nich mieści, podejmuje decyzje sam. Jeśli je przekroczy (tzw. wyjątek), sprawa trafia wyżej – do Komitetu Sterującego.
		6. Orientacja na produkty: Skupienie się na definicji jakościowej produktów i ich odbiorach, a nie tylko na samych czynnościach/pracy.
		7. Dostosowanie do warunków projektu: Metodyka nie jest sztywnym szablonem; musi być dopasowana do rozmiaru, złożoności i specyfiki projektu.

2. Standard PMI / PMBOK (Project Management Institute)
	• PMI: Międzynarodowa organizacja typu non-profit skupiająca profesjonalistów zarządzania projektami (powstała w USA w 1969 r., w Polsce od 2003 r.). Wydaje standard PMBOK Guide.
	• Tradycyjne ujęcie (PMBOK 6 edycja i wcześniejsze):
		○ Opiera się na podziale na procesy, cykle życia oraz 10 Obszarów Wiedzy (Zarządzanie: Integracją, Zakresem, Czasem, Kosztem, Jakością, Zasobami, Komunikacją, Ryzykiem, Zamówieniami, Interesariuszami).
	• Ewolucja standardu (PMBOK 7 i 8 edycja):
		○ Mocne przesunięcie w kierunku podejść zwinnych i hybrydowych. Koncentracja na dostarczaniu wartości (Value), a nie tylko na ścisłym realizowaniu procesów planistycznych.
