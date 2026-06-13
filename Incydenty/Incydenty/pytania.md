# 1.

Ile atrybutów przepływu (flow) wymienia rejestr organizacji IANA dla podmiotów IPFIX i które z nich są stosowane najpowszechniej?

- **Wymienia ich kilkaset, z czego pierwsze 128 jest stosowanych najpowszechniej.**
- Wymienia dokładnie 128 atrybutów i wszystkie są używane z taką samą częstotliwością.
- Wymienia ponad 1000 atrybutów, z czego pierwsze 256 stanowi podstawę analizy.
- Wymienia kilkadziesiąt atrybutów, z których pierwsze 10 określa standard komunikacji.

# 2.

W jaki sposób protokół NetFlow pomaga analitykowi bezpieczeństwa podczas badania incydentu sieciowego?

- Służy do automatycznego blokowania złośliwego oprogramowania i bezpośredniej inspekcji zawartości pakietów (payload) w czasie rzeczywistym.
- **Pozwala na odtworzenie osi czasu naruszenia bezpieczeństwa, zrozumienie zachowania hostów oraz śledzenie przemieszczania się napastnika wewnątrz sieci.**
- Służy do szyfrowania ruchu wychodzącego w celu zapobiegania wyciekom danych (DLP).
- Umożliwia weryfikację reputacji domen DNS i filtrowanie złośliwych załączników w wiadomościach e-mail.

# 3.

Które ze stwierdzeń najlepiej oddaje charakterystykę zawartości (payload) w rekordach telemetrycznych typu NetFlow?

- NetFlow zapisuje pierwsze 62 bajty danych właściwych dla każdej sesji, aby umożliwić analizę kodu exploitów.
- Pełna zawartość pakietów (payload) jest dołączana do rekordu tylko wtedy, gdy w sesji wystąpią flagi TCP takie jak SYN i FIN.
- **Rekordy NetFlow nie zawierają treści właściwej (payload) komunikacji, a jedynie statystyki i metadane dotyczące sesji sieciowych.**
- Zawartość payloadu jest dostępna wyłącznie w Flexible NetFlow, podczas gdy starsze wersje jej nie obsługiwały.

# 4.

Na podstawie jakich danych silnik rozpoznawania aplikacji NBAR2 jest w stanie zidentyfikować w sieci usługi takie jak Skype, YouTube czy ruch P2P?

- Wyłącznie na podstawie numerów portów transportowych warstwy 4 (L4).
- **Przy użyciu danych z warstw od L3 do L7 modelu OSI.**
- Korzystając wyłącznie z adresów IP warstwy sieciowej (L3).
- Na podstawie zewnętrznych zapytań weryfikacyjnych wysyłanych do DNS super proxy.

# 6.

W jaki sposób systemy filtrowania zawartości Cisco ESA oraz WSA ułatwiają personelowi monitorującemu uzyskanie szczegółowych informacji z logów?

- **Umożliwiają klikanie komponentów raportów ogólnych (Overview) w celu wyświetlenia szczegółów oraz stosowanie wyszukiwania celowanego.**
- Automatycznie tłumaczą każdą mnemotechnikę błędu na komendy konfiguracyjne routera.
- Wymuszają stosowanie zewnętrznych narzędzi typu nfdump do odczytania jakichkolwiek szczegółów.
- Wysyłają ukryte powiadomienia PRI do bazy DNS super proxy przy każdym kliknięciu.

# 7.

Gdzie dokładnie w strukturze komunikatu Syslog (np. z systemu Cisco ASA lub IOS) znajduje się specyficzna wartość "Cisco Facility" (taka jak ASA lub SYS)?

- Jest zapisana wyłącznie w ukrytym standardowym nagłówku pakietu, zwanym polem PRI.
- Znajduje się na samym końcu komunikatu, tuż za pełnym tekstem opisu zdarzenia (Message Text).
- Występuje w sekcji HEADER pomiędzy znacznikiem czasu (Timestamp) a strefą czasową EDT.
- **Pojawia się bezpośrednio w części tekstowej komunikatu (sekcji MSG) i następuje po znaku '%'.**

![[Pasted image 20260613191438.png]]
# 8.

W logu urządzenia Cisco IOS o treści: %SYS-5-CONFIG_I: Configured from console by con0, czym jest cyfra 5 umieszczona pomiędzy słowem SYS a CONFIG_I?

- **Określa poziom ważności zdarzenia (Severity), który w tym przypadku oznacza powiadomienie (Notification).**
- Jest to unikalny identyfikator Message ID, służący do odszukania błędu w dokumentacji technicznej.
- Oznacza liczbę pakietów, które zostały przesłane w trakcie trwania tej sesji konfiguracji.
- Wskazuje na numer fizycznego interfejsu (np. FastEthernet 0/5), z którego dokonano modyfikacji.

# 9.

Do jakich kluczowych celów analitycznych można wykorzystać logi generowane przez serwery proxy (np. web proxy lub DNS proxy)?

- Do bezpośredniego pomiaru metryk jakościowych łącza, takich as opóźnienie (latency) czy utrata pakietów.
- Do automatycznej synchronizacji zegarów systemowych urządzeń za pomocą statusu NTP.
- **Do ustalenia, które hosty wysyłają zapytania, czy miejsca docelowe są bezpieczne oraz do uzyskania wglądu w rodzaj pobieranych zasobów.**
- Do konfiguracji polityk QoS na interfejsach szeregowych routerów brzegowych.

![[Pasted image 20260613191646.png]]
# 17.

Zgodnie ze standardami dostępności (tzw. regułą dziewiątek), jaki poziom dostępności jest wymagany dla systemów SOC, zapór NGFW i infrastruktury korporacyjnej klasy Enterprise?

- 99% (dopuszczający do 3 dni i 15 godzin przestoju w roku).
- 99.9% (dopuszczający do 8 godzin i 45 minut przestoju w roku).
- **99.99% (dopuszczający do 52 minut i 35 sekund przestoju w roku).**
- 99.9999% (dopuszczający maksymalnie do 31 sekund przestoju w roku).

![[Pasted image 20260613191739.png]]
# 18.

Która technologia z ekosystemu SOC odpowiada za filtrowanie i monitorowanie ruchu HTTP/HTTPS w celu ochrony warstwy 7 (aplikacyjnej) m.in. przed atakami SQL Injection oraz Cross-Site Scripting (XSS)?

- IPS (Intrusion Prevention System).
- **WAF (Web Application Firewall).**
- Secure Web Gateway (Proxy).
- EDR (Endpoint Detection and Response).

![[Pasted image 20260613191835.png]]
# 22.

Która warstwa trójwarstwowego hierarchicznego modelu projektowania sieci LAN odpowiada za zapewnienie użytkownikom i urządzeniom końcowym bezpośredniego dostępu do sieci?

- Warstwa rdzenia (Core Layer).
- Warstwa dystrybucji (Distribution Layer).
- **Warstwa dostępu (Access Layer).**
- Warstwa transportowa (Transport Layer).

![[Pasted image 20260613191916.png]]
# 27.

Jaka jest główna wada systemu wykrywania włamań typu IDS (Intrusion Detection System) w porównaniu do systemów IPS?

- Powoduje stałe opóźnienia (latencje) w sieci przez głęboką analizę każdego pakietu w trybie inline.
- Każda awaria lub przeciążenie czujnika IDS skutkuje całkowitym odcięciem ruchu i paraliżem sieci.
- **Nie może samodzielnie zatrzymać pojedynczego pakietu przed dotarciem do celu (działa w trybie wykrywania, a nie blokowania).**
- Wymaga instalacji dedykowanego oprogramowania na każdym urządzeniu końcowym z osobna.

# 43.

Jaka jest główna różnica funkcjonalna pomiędzy wskaźnikami IOC (Indicators of Compromise) a IOA (Indicators of Attack)?

- IOC mają podejście proaktywne i badają intencje, natomiast IOA mają podejście reaktywne i badają pliki historyczne.
- **IOC skupiają się na pytaniu „Co się stało?” (podejście reaktywne), a IOA skupiają się na „Co się teraz dzieje i dlaczego?” (podejście proaktywne).**
- IOC służą wyłącznie do ochrony sieci Wi‑Fi, podczas gdy IOA filtrują ruch w sieciach LAN.
- IOC są wykorzystywane przez system Kali Linux, a IOA są unikalne dla systemu Security Onion.

# 50.

Który z poniższych złośliwych programów jest klasyfikowany jako botnet/trojan, którego głównym zadaniem jest rozsyłanie spamu oraz ułatwianie instalacji oprogramowania ransomware?

- Agent Tesla.
- RedLine.
- NanoCore.
- **Emotet.**

![[Pasted image 20260613192212.png]]
# 65.

Zgodnie z wytycznymi, każda podatność o jakim wyniku punktowym w klasyfikacji CVSS powinna zostać bezwzględnie wyeliminowana?

- **Każda podatność przekraczająca wartość 3.9.**
- Tylko podatności o wyniku równym dokładnie 10.0.
- Podatności z przedziału od 0.1 do 1.5.
- Wyłącznie te, które posiadają klasę 0.

![[Pasted image 20260613192300.png]]
# 73.

Analiza logów których protokołów sieciowych pozwala analitykowi SOC na jednoznaczne zidentyfikowanie tzw. „Pacjenta Zero” (Patient Zero) w przypadku infekcji malware dostarczonym drogą pocztową?

- DNS oraz NTP
- Syslog oraz ICMP
- **SMTP, POP3 oraz IMAP**
- HTTP oraz HTTPS

# 76.

W jaki sposób technologia PAT (Port Address Translation) wpływa na monitorowanie bezpieczeństwa sieci i analizę danych NetFlow?

- Automatycznie szyfruje wszystkie nagłówki pakietów warstwy transportowej.
- Ułatwia wykrywanie anomalii poprzez wymuszenie stałej struktury piątki parametrów (five-tuple).
- **Komplikuje monitorowanie, ponieważ ruch z wielu różnych urządzeń wewnętrznych współdzieli ten sam publiczny adres IP, utrudniając identyfikację konkretnego hosta.**
- Wyłącza możliwość rejestrowania logów typu Connection Event na zaporach NGFW.

# 5.

Jakie specyficzne metryki są zbierane w ramach funkcjonalności "Metrics Collection" w celu ich późniejszego eksportu do narzędzi zarządzających?

- **Wykorzystanie przepustowości, czas odpowiedzi, opóźnienie, utrata pakietów oraz jitter.**
- Zawartość wiadomości e-mail, reputacja domen oraz kody błędów aplikacji webowych.
- Nazwy zalogowanych użytkowników, typy systemów operacyjnych oraz unikalne sygnatury plików.
- Reguły systemu NGIPS oraz kategorie tematyczne filtrowania adresów URL.

![[Pasted image 20260613192503.png]]
# 10.

Na czym polega funkcja zapobiegania wyciekom danych (DLP – Data Loss Prevention) realizowana przy użyciu serwerów web proxy?

- **Na skanowaniu ruchu wychodzącego w celu wykrycia, czy opuszczające sieć dane zawierają informacje wrażliwe, poufne lub tajemnice firmy.**
- Na blokowaniu ruchu przychodzącego, który próbuje sfałszować nagłówki Syslog w sekcji MSG.
- Na nadawaniu priorytetów pakietom głosowym i wideo w celu maksymalizacji wolumenu przesyłanych danych.
- Na weryfikacji, czy odpowiedzi z sieci nie zostały zmanipulowane i nie stanowią exploitów atakujących przeglądarkę klienta.

![[Pasted image 20260613192542.png]]
# 11.

Czym różnią się zapory sieciowe nowej generacji (NGFW) wyposażone w usługi Firepower Services od tradycyjnych, starszych zabezpieczeń sieciowych?

- Opierają swoją architekturę detekcji wyłącznie na pasywnym zbieraniu statystyk NetFlow v9 oraz Flexible NetFlow.
- Do wyświetlenia jakichkolwiek interaktywnych raportów na panelach kontrolnych wymagają bezwzględnego wdrożenia zewnętrznego systemu SIEM.
- Analizują ruch sieciowy wyłącznie w oparciu o adresy IP i numery portów warstwy transportowej (L4).
- **Rozszerzają bezpieczeństwo do warstwy aplikacji i wyższych, konsolidując funkcje takie jak AVC, NGIPS, filtrowanie URL oraz zaawansowaną ochronę przed malware (AMP).**

# 12.

Które trzy kluczowe elementy składają się na strukturę i funkcjonowanie nowoczesnego centrum operacji bezpieczeństwa (SOC)?

- Dane, Szyfrowanie, Polityka.
- **Ludzie, Procesy, Technologie.**
- Sprzęt, Oprogramowanie, Budżet.
- Serwery, Przepustowość, Sygnatury.

![[Pasted image 20260613192728.png]]
# 13.

Analityk SOC z poziomu Tier 1 (Alert Analyst) zweryfikował, że dany alert sieciowy to rzeczywisty incydent, ale nie potrafi samodzielnie rozwiązać problemu. Jaki powinien być jego kolejny krok?

- Zamknięcie zgłoszenia w systemie ticketingowym jako fałszywy alarm (false positive).
- Przekazanie zgłoszenia bezpośrednio do SOC Managera w celu poinformowania klienta.
- **Eskalacja zgłoszenia do zespołu Tier 2 Incident Responder w celu pogłębionej analizy.**
- Przesłanie wskaźników kompromitacji (IoC) bezpośrednio do otwartej społeczności MISP.

# 14.

Czym zajmują się specjaliści na poziomie Tier 3 (Threat Hunter) w strukturach nowoczesnego SOC?

- Bieżącym monitorowaniem kolejek alertów i otwieraniem zgłoszeń (tickets) dla każdego zdarzenia.
- **Proaktywnym wyszukiwaniem w sieci cyberzagrożeń, które nie zostały dotąd wykryte przez standardowe systemy bezpieczeństwa.**
- Konfiguracją polityk jakości usług (QoS) na zaporach sieciowych nowej generacji.
- Zarządzaniem zasobami ludzkimi, budżetem operacyjnym SOC oraz kontaktem z mediami.

![[Pasted image 20260613192824.png]]
# 15.

Jaka jest główna różnica w działaniu systemów klasy SOAR w porównaniu do tradycyjnych systemów SIEM?

- SOAR służy wyłącznie do zbierania logów, podczas gdy SIEM odpowiada za deszyfrowanie ruchu SSL/TLS.
- **Systemy SOAR dodatkowo integrują dane z threat intelligence oraz automatyzują procesy robocze (workflows) za pomocą scenariuszy (playbooks).**
- SIEM wymaga instalacji drogich agentów sprzętowych, a SOAR działa wyłącznie jako usługa darmowa typu Open Source.
- SOAR służy do monitorowania fizycznego dostępu do budynków, podczas gdy SIEM analizuje tylko ruch w chmurze.

![[Pasted image 20260613192922.png]]
# 16.

Jak w terminologii metryk SOC definiuje się wskaźnik o nazwie "Dwell Time"?

- Średni czas potrzebny na odizolowanie zainfekowanego hosta i powstrzymanie wycieku danych.
- Średni czas wymagany przez personel na zidentyfikowanie krytycznego incydentu.
- **Czas, przez jaki aktorzy zagrożeń (threat actors) dysponują aktywnym dostępem do sieci, zanim zostaną wykryci, a ich dostęp – zablokowany.**
- Czas potrzebny na automatyczne wygenerowanie raportu z testów penetracyjnych przez systemy SOAR.

![[Pasted image 20260613193037.png]]
# 19.

Jaki scenariusz zagrożenia fizycznego jest wykrywany, gdy algorytmy analizy obrazu (np. w systemie iProtect) rejestrują wejście dwóch osób przez strefę buforową, podczas gdy urządzenie obwodowe zarejestrowało autoryzację tylko jednego identyfikatora?

- Impossible Travel (Niemożliwa podróż)
- **Tailgating (Omijanie zabezpieczeń / podążanie za kimś).**
- False Positive (Fałszywy alarm systemowy)
- SQL Injection w warstwie fizycznej

![[Pasted image 20260613193203.png]]
# 20.

Czym charakteryzuje się egzamin na certyfikat OSCP (Offensive Security Certified Professional)?

- Jest testem jednokrotnego wyboru składającym się ze 100 pytań zamkniętych typu ABCD.
- **Trwa 48 godzin, podczas których kandydat ma 24 godziny na przełamanie zabezpieczeń maszyn w labie i kolejne 24 godziny na napisanie profesjonalnego raportu.**
- Polega na ustnej obronie projektu przed komisją ekspertów z organizacji Cisco.
- Wymaga wyłącznie pasywnego wyklikiwania gotowych scenariuszy (playbooks) w środowisku SOAR.

# 21.

Jaka jest główna różnica pomiędzy topologią fizyczną (Physical topology) a topologią logiczną (Logical topology) w dokumentacji sieciowej?

- Topologia fizyczna opisuje działanie zapór sieciowych, a logiczna – systemów IDS/IPS.
- **Topologia fizyczna przedstawia rzeczywiste rozmieszczenie urządzeń (np. szafy RACK) i tras kablowych, natomiast logiczna koncentruje się na przepływie danych, logicznych interfejsach i adresacji IP.**
- Topologia logiczna określa fizyczne trasy instalacji w serwerowni, a fizyczna – schemat podsieci i VLAN-ów.
- Topologia fizyczna jest stosowana wyłącznie w sieciach typu Enterprise, a logiczna tylko w małych sieciach domowych.

# 23.

Mniejsze środowiska korporacyjne często wykorzystują dwuwarstwową architekturę "zwiniętego rdzenia" (Collapsed Core). Na czym ona polega?

- Na całkowitym wyeliminowaniu warstwy dostępu w celu oszczędności finansowych.
- **Na połączeniu warstwy rdzenia i warstwy dystrybucji w jedną wspólną warstwę w celu redukcji kosztów i złożoności.**
- Na zastąpieniu tradycyjnych przełączników przewodowych bezprzewodowymi routerami SOHO.
- Na awaryjnym wyłączeniu zapasowych połączeń redundantnych w strukturze sieci.

![[Pasted image 20260613193414.png]]
# 24.

W kontekście projektowania zapór sieciowych, które interfejsy są wykorzystywane w tradycyjnym modelu Strefy Zdemilitaryzowanej (DMZ)?

- Wyłącznie interfejs publiczny (Public) oraz interfejs prywatny (Private).
- Interfejs wejściowy (Ingress), wyjściowy (Egress) oraz port monitorujący (SPAN).
- **Interfejs wewnętrzny (Inside), zewnętrzny (Outside) oraz interfejs DMZ stanowiący wydzieloną strefę buforową.**
- Interfejs wirtualny (VLAN), interfejs fizyczny (NIC) oraz logiczny punkt styku.

![[Pasted image 20260613193559.png]]
# 25.

Która z poniższych cech prawidłowo opisuje bezstanowe filtrowanie pakietów (Stateless Firewall)?

- **A. Każda paczka danych jest oceniana osobno, bez kontekstu poprzednich pakietów i bez analizy sesji.**
- B. Śledzi stan aktywnych połączeń sieciowych przy użyciu zaawansowanej tabeli stanów (state table).
- C. Działa głównie w warstwie 7 (Aplikacji) modelu OSI, całkowicie rozumiejąc komendy protokołów.
- D. Automatycznie przepuszcza ruch powrotny, wnioskując o nim wyłącznie na podstawie historii sesji.

# 26.

Jaką funkcjonalnością wyróżniają się nowoczesne zapory nowej generacji (NGFW) w porównaniu do tradycyjnych firewalli stanowych?

- Filtrują ruch wyłącznie w oparciu o adresy fizyczne MAC w warstwie 2 modelu OSI.
- **Posiadają świadomość aplikacji, zintegrowany system IPS oraz wsparcie dla analizy w chmurze i sandboxingu.**
- Są instalowane wyłącznie jako oprogramowanie bezpośrednio na systemie operacyjnym konkretnego komputera.
- Nie wpływają w żaden sposób na wydajność i są całkowicie odporne na błędy konfiguracyjne.

# 28.

Systemy HIPS (Host-based IPS) mają istotną zaletę w porównaniu do systemów NIPS (Network-based IPS). Które z poniższych zdań opisuje tę zaletę?

- Mogą chronić cały segment sieci korporacyjnej za pomocą jednego centralnego urządzenia.
- **Mogą analizować ruch zaszyfrowany, ponieważ mają do niego dostęp po deszyfracji przez system operacyjny hosta.**
- Są całkowicie niewidoczne dla potencjalnych napastników i nie zużywają zasobów procesora maszyny.
- Nie wymagają precyzyjnego dostrojenia, całkowicie eliminując problem fałszywych alarmów (False Positives).

![[Pasted image 20260613193734.png]]
# 29.

Do jakich zadań dedykowane jest wyspecjalizowane urządzenie bezpieczeństwa o nazwie Cisco Web Security Appliance (WSA)?

- Do ochrony przed zaawansowanym malware typu APT poprzez ciągłą analizę retrospektywną plików.
- Do bezpieczeństwa poczty elektronicznej (SMTP), blokowania spamu oraz szyfrowania wiadomości wychodzących.
- **Do bezpieczeństwa WWW (Proxy), oferując filtrowanie adresów URL, skanowanie malware w czasie rzeczywistym i kontrolę aplikacji.**
- Do monitorowania parametrów środowiskowych w fizycznych centrach danych SOC.

![[Pasted image 20260613193842.png]]
# 30.

Jaki rodzaj listy kontroli dostępu (ACL) w systemie Cisco IOS należy zastosować, jeśli chcemy zablokować ruch konkretnego typu (np. protokół ICMP), a nie tylko cały ruch IP?

- Standardową listę ACL (Standard ACL), ponieważ bada ona porty warstwy transportowej.
- **Rozszerzoną listę ACL (Extended ACL), ponieważ standardowa ACL analizuje wyłącznie źródłowy adres IP i nie rozumie protokołów.**
- Listę ACL warstwy 2, ponieważ protokół ICMP jest hermetyzowany bezpośrednio w ramkach Ethernet.
- Listę ACL typu established, która służy wyłącznie do filtrowania ruchu bezstanowego.

# 31.

Wskaż składnię (komendę) systemu Linux (iptables), która służy do zablokowania ruchu sieciowego pochodzącego z adresu IP 192.168.1.10

- access-list 1 deny host 192.168.1.10
- **iptables -A INPUT -s 192.168.1.10 -j DROP**
- term BLOCK-IP { from { source-address 192.168.1.10/32; } then discard; }
- /ip firewall filter add chain=input src address=192.168.1.10 action=drop

![[Pasted image 20260613193953.png]]
# 32.

W jaki sposób mechanizmy filtrujące ruterów/firewalli weryfikują, czy pakiet TCP jest odpowiedzią na nasze wewnętrzne zapytanie (np. do serwera WWW)?

- **Wykorzystują reguły sprawdzające stan sesji, np. flagę established w Cisco IOS lub stan ESTABLISHED w iptables**
- Wymagają wysłania zapytania kontrolnego ICMP Echo Request do serwera źródłowego w celu potwierdzenia tożsamości
- Domyślnie blokują każdy ruch powrotny, zmuszając użytkownika do nawiązania sesji przez VPN
- Przekierowują nagłówek pakietu do bazy Cisco Talos w celu weryfikacji sumy kontrolnej

# 33.

Z jakich komponentów składa się system zarządzania siecią oparty na protokole SNMP (Simple Network Management Protocol)?

- Z relacyjnych baz danych SQL oraz agentów bezstanowych
- **Z Menedżera SNMP (urządzenie/serwer NMS) oraz Agentów SNMP działających na monitorowanych węzłach sieciowych**
- Ze skryptów automatyzujących w języku Python oraz kolektorów logów typu SIEM
- Z portów wejściowych (Ingress) oraz dedykowanych sensorów typu Inline

# 34.

Jaka jest zasada działania i cel stosowania technologii Cisco NetFlow w strukturach sieciowych?

- Służy do tworzenia dokładnych kopii całego ruchu sieciowego i przesyłania ich na port diagnostyczny
- **Monitoruje połączenia aplikacji, śledzi statystyki pakietów oraz bajtów dla indywidualnych przepływów (flows) i przesyła je do serwera NetFlow Collector**
- Odpowiada za sprzętowe deszyfrowanie ruchu SSL/TLS na brzegu sieci korporacyjnej
- Wymusza polityki kontroli dostępu do sieci w oparciu o fizyczną lokalizację szafy RACK

# 35.

Podczas konfiguracji monitorowania portów (Port Mirroring / SPAN), czym charakteryzuje się port docelowy (Destination / Monitoring Port)?

- Może bez problemu obsługiwać normalny ruch sieciowy użytkowników i jednocześnie odbierać kopie pakietów
- Służy wyłącznie do nasłuchiwania ruchu rozgłoszeniowego (Broadcast) wewnątrz jednej podsieci
- **Zazwyczaj przestaje działać jako normalny port sieciowy – służy wyłącznie do odbierania kopii danych na potrzeby systemów IDS lub snifferów**
- Musi być logicznym interfejsem tunelowym typu L3 VPN o wysokiej latencji

# 37.

Jeśli organizacja decyduje się na zakup polisy ubezpieczeniowej, aby pokryć potencjalne straty finansowe wywołane cyberatakiem, to jaką strategię zarządzania ryzykiem realizuje?

- Akceptacja ryzyka (Risk acceptance).
- Unikanie ryzyka (Risk avoidance).
- Redukcja ryzyka (Risk reduction).
- **Transfer ryzyka (Risk transfer).**

![[Pasted image 20260613194440.png]]
# 38.

Do których grup hakerów odnosi się oficjalny termin „podmiot stwarzający zagrożenie” (Threat actor) zgodnie z uwagami w materiale?

- Wyłącznie do białych hakerów (White Hat).
- **Do osób lub grup, które można zaklasyfikować jako szarych lub czarnych hakerów.**
- Wyłącznie do nastolatków typu "script kiddies", którzy nie szukają zysku finansowego.
- Do certyfikowanych audytorów bezpieczeństwa pracujących w zespołach Blue Team.

![[Pasted image 20260613194642.png]]
# 39.

Kim według podziału na typy hakerów są tzw. szarzy hakerzy (Gray Hat)?

- To etyczni hakerzy, którzy działają wyłącznie w pełni legalnie i za zgodą właściciela systemu.
- To nieetyczni przestępcy, którzy naruszają bezpieczeństwo systemów wyłącznie dla własnych korzyści materialnych.
- **To osoby, które popełniają przestępstwa i podejmują nieetyczne działania, ale nie robią tego dla osobistych korzyści ani w celu wyrządzenia szkód.**
- To etatowi pracownicy agencji rządowych odpowiedzialni za cyber-sabotaż obcych państw.

# 40.

Jak nazywamy podmiot (najczęściej klasyfikowany jako szary haker), którego celem jest odkrywanie exploitów i zgłaszanie ich bezpośrednio dostawcom oprogramowania w zamian za nagrody (np. w programach Bug Bounty)?

- Haktywista (Hacktivist).
- Script kiddie.
- Cyberprzestępca (Cybercriminal).
- **Broker podatności (Vulnerability broker).**

# 41.

Na czym polegał historyczny atak przeprowadzony przez Johna Drapera (Captain Crunch) za pomocą słynnego gwizdka z płatków śniadaniowych o częstotliwości 2600 Hz?

- Sygnał dźwiękowy zmuszał urządzenie końcowe do zresetowania hasła administratora.
- **Oszukiwał centralę telefoniczną, że użytkownik odłożył słuchawkę, co pozwalało na bezpłatne wykonywanie dalszych połączeń na koszt operatora.**
- Blokował mechanicznie wrzutnik monet w budkach telefonicznych poprzez przeciążenie sensora audio.
- Generował fałszywy klucz szyfrujący dla pierwszych modemów szerokopasmowych.

# 42.

Jakie działanie charakteryzowało urządzenia nazywane przez hakerów w latach 80. jako Red Box?

- Automatycznie wybierały tysiące numerów telefonów w celu poszukiwania aktywnych modemów.
- **Odtwarzały do słuchawki specyficzne sekwencje tonów (np. 1700 Hz i 2200 Hz), udając wrzucenie monet do automatu telefonicznego.**
- Służyły do łamania haseł w systemach typu BBS metodą słownikową.
- Przechwytywały pakiety danych przesyłane drogą radiową.

![[Pasted image 20260613194918.png]]
# 44.

Co znajduje się na samym szczycie Piramidy Bólu (Pyramid of Pain) Davida J. Bianco, stanowiąc element, którego zablokowanie kosztuje hakera najwięcej trudu i miesięcy pracy?

- Sumy kontrolne plików (Hashes).
- Adresy IP serwerów C2.
- Nazwy domen (Domain names).
- **Taktyki, Techniki i Procedury (TTPs).**

![[Pasted image 20260613195112.png]]
# 45.

Porównując dwa popularne systemy bezpieczeństwa – Kali Linux oraz Security Onion – który z nich pełni rolę defensywną (pasywną) i jest przeznaczony dla analityków SOC (Blue Teamerów)?

- Kali Linux, ponieważ wysyła aktywne pakiety testowe do celu.
- **Security Onion, ponieważ służy do obrony, monitorowania sieci oraz pasywnego nasłuchiwania ruchu.**
- Oba systemy są wyłącznie systemami ofensywnymi używanymi przez zespoły Red Team.
- Żaden z nich, ponieważ analitycy SOC pracują wyłącznie na systemach Windows Server.

# 46.

Do czego służą w cyberbezpieczeństwie narzędzia nazywane fuzzerami (np. AFL, Peach Fuzzer)?

- Do automatycznego odzyskiwania haseł za pomocą tablic tęczowych (Rainbow Tables).
- Do masowego wysyłania spamu i przeprowadzania ataków phishingowych.
- **Do automatycznego testowania oprogramowania poprzez wprowadzanie ogromnej ilości nieoczekiwanych, błędnych lub losowych danych w celu wywołania błędu/awarii.**
- Do bezpiecznego usuwania logów systemowych z serwerów Linux.

# 47.

W jakiej kategorii narzędzi hackerskich znajdują się programy takie jak Hping, Scapy, Nemesis czy Netcat, wykorzystywane do testowania wytrzymałości firewalli?

- Skanery podatności (Vulnerability scanners).
- **Narzędzia do tworzenia pakietów (Packet crafting)**.
- Detektory rootkitów (Rootkit detectors).
- Łamacze haseł (Password crackers).

![[Pasted image 20260613195649.png]]
# 48.

Jak definiowany jest atak typu spoofing adresu IP (IP address spoofing attack)?

- Przechwytywanie i ciągłe monitorowanie ruchu bez modyfikacji zawartości pakietów.
- Umieszczenie się atakującego bezpośrednio na ścieżce komunikacji między użytkownikiem a serwerem banku.
- Przejęcie loginu i hasła użytkownika w celu zalogowania się na jego konto pracownicze.
- **Spreparowanie pakietu IP w taki sposób, aby wyglądał on na wysłany z prawidłowego, zaufanego adresu wewnątrz sieci korporacyjnej.**

# 49.

Do czego służy popularny serwis internetowy haveibeenpwned.com?

- Do automatycznego generowania silnych haseł kryptograficznych.
- **Do sprawdzania, czy nasz adres e‑mail lub hasło nie pojawiły się w znanych wyciekach lub opublikowanych bazach danych.**
- Do przeprowadzania testów penetracyjnych sieci Wi‑Fi w trybie online.
- Do weryfikacji poprawności konfiguracji rekordów SPF i DKIM dla domeny pocztowej.

# 51.

Jaka komenda w środowisku PowerShell systemu Windows pozwala na wygenerowanie sumy kontrolnej pliku przy użyciu algorytmu SHA256?

- sha256sum plik
- **Get-FileHash "C:\sciezka\plik.exe" -Algorithm SHA256**
- Get-Checksum -File plik.exe -Type SHA256
- Format-List -Path plik.exe -Hash SHA256

# 52.

Jak brzmi polecenie w systemie Linux służące do szybkiego obliczenia skrótu SHA256 dla wybranego pliku?

- **sha256sum plik**
- md5sum -sha256 plik
- get-hash --sha256 plik
- certutil -hashfile plik SHA256

# 53.

Na czym polega działanie mechanizmu bezpieczeństwa poczty e-mail o nazwie SPF (Sender Policy Framework)?

- Na cyfrowym podpisywaniu każdej wiadomości kluczem prywatnym nadawcy
- Na blokowaniu wiadomości zawierających załączniki z rozszerzeniem .exe
- **Na udostępnieniu ograniczonej, autoryzowanej listy adresów IP, z których dany serwer może wysyłać maile w imieniu domeny**
- Na automatycznym szyfrowaniu treści wiadomości za pomocą algorytmu AES-256

# 54.

W jaki sposób mechanizm DKIM (DomainKeys Identified Mail) weryfikuje autentyczność pochodzenia wiadomości e-mail?

- **Serwer wysyłający podpisuje maila kluczem prywatnym, a serwer odbiorcy pobiera klucz publiczny z DNS nadawcy i sprawdza, czy podpis pasuje**
- Wymusza od użytkownika wpisanie jednorazowego kodu SMS przed wysłaniem wiadomości
- Porównuje geolokalizację IP nadawcy z adresem fizycznym firmy zarejestrowanym w KRS
- Wysyła zapytanie zwrotne do serwera nadawcy w celu potwierdzenia hasła użytkownika

![[Pasted image 20260613200036.png]]
# 55.

Co jest główną zaletą rozwiązania DKIM w porównaniu do innych metod weryfikacji poczty?

- Całkowicie eliminuje potrzebę stosowania filtrów antyspamowych na serwerze
- Szyfruje całą zawartość maila, uniemożliwiając jego odczytanie osobom trzecim
- **Nawet jeśli mail przejdzie przez dziesięć serwerów pośredniczących, podpis DKIM pozostaje nienaruszony i potwierdza autentyczność**
- Automatycznie usuwa złośliwe linki i załączniki z treści wiadomości

# 56.

Co oznacza instrukcja p=quarantine w polityce konfiguracyjnej mechanizmu DMARC?

- „Dostarcz maila normalnie do skrzynki odbiorczej, ale daj mi znać w raporcie zbiorczym”.
- **„Jeśli test SPF/DKIM zawiedzie, wrzuć tego maila do folderu ze Spamem (kwarantanny)”.**
- „Jeśli domena nie posiada podpisu, całkowicie usuń konto nadawcy z serwera”.
- „Zablokuj możliwość wysyłania jakichkolwiek wiadomości e‑mail z tej domeny na 48 godzin”.

![[Pasted image 20260613200154.png]]
# 57.

Jeśli administrator ustawi regułę DMARC na poziom p=reject, jak zachowa się serwer pocztowy odbiorcy w przypadku wykrycia sfałszowanej wiadomości?

- Przepuści maila, oznaczając go w temacie czerwoną flagą ostrzegawczą.
- Przekieruje wiadomość bezpośrednio na skrzynkę działu IT/bezpieczeństwa.
- **W ogóle nie przyjmie tego maila, odrzucając go na progu.**
- Odeśle maila z powrotem do nadawcy z prośbą o ponowne ręczne podpisanie.

# 58.

Jakie jest ważne zadanie analityka cyberbezpieczeństwa w odniesieniu do alertów generowanych przez urządzenia sieciowe, takie jak firewalle i systemy IPS?

- Automatyczne usuwanie wszystkich logów starszych niż 30 dni bez ich analizy.
- **Przeglądanie wszystkich alertów i określanie ich zasadności.**
- Samodzielne pisanie nowych sygnatur w języku Python bezpośrednio w kodzie jądra systemu dla każdego alertu.
- Wyłączanie urządzeń bezpieczeństwa w przypadku wykrycia jakichkolwiek fałszywych alarmów (False Positives).

# 59.

Czym charakteryzuje się metoda przechwytywania ruchu znana jako Network TAP?

- Jest to logiczny port konfigurowany wyłącznie na przełącznikach wielowarstwowych.
- **To fizyczne urządzenie wpięte bezpośrednio w linię transmisyjną (szeregowo/inline) pomiędzy badanym urządzeniem a siecią.**
- To oprogramowanie antywirusowe zainstalowane bezpośrednio na końcowym urządzeniu użytkownika.
- To dedykowana usługa chmurowa służąca do maskowania adresów MAC.

![[Pasted image 20260613200349.png]]
# 60.

Co oznacza, że urządzenia typu Network TAP charakteryzują się bezpieczeństwem typu „fail‑safe”?

- W przypadku wykrycia złośliwego oprogramowania urządzenie automatycznie odcina cały ruch sieciowy.
- **W przypadku awarii zasilania lub samego Tapa połączenie fizyczne między zaporą ogniową (firewall) a routerem pozostaje nienaruszone – ruch sieciowy przepływa dalej.**
- Urządzenie potrafi automatycznie korygować i naprawiać uszkodzone pakiety warstwy fizycznej.
- Gwarantuje ono, że napastnik nie będzie w stanie przeprowadzić udanego ataku typu IP Spoofing.

![[Pasted image 20260613200439.png]]
# 61.

Na czym polega wykrywanie zagrożeń oparte na anomaliach (Anomaly-based) w systemach HIDS?

- Na ciągłym przeszukiwaniu internetu w celu znalezienia nowych exploitów zero-day.
- **Na porównywaniu bieżącego zachowania hosta z wyuczonym modelem bazowym (baseline) normalnego zachowania.**
- Na automatycznym blokowaniu wszystkich pakietów przesyłanych protokołem UDP.
- Na ręcznym dopisywaniu adresów IP do czarnych list przez analityka SOC.

# 62.

W jaki sposób system OSSEC (HIDS) realizuje funkcję aktywnej reakcji (active response) po wykryciu ataku Brute Force na SSH?

- Wysyła zapytanie do bazy CVE w celu analizy kodu źródłowego.
- Przenosi całą maszynę do chmury Cisco Meraki.
- **Uruchamia skrypt automatycznie blokujący adres IP agresora za pomocą lokalnej zapory (np. iptables).**
- Usuwa plik logów /var/log/auth.log, aby haker nie miał dostępu do danych.

# 63.

Czym jest powierzchnia ataku (Attack Surface) organizacji?

- **Całkowitą sumą wszystkich podatności w systemie, które są dostępne dla atakującego.**
- Liczbą fizycznych zabezpieczeń zainstalowanych w serwerowni.
- Listą kwalifikowanych dostawców usług zaufania wpisanych na listę TSL.
- Przedziałem punktowym w systemie CVSS przypisanym do luk o statusie krytycznym.

# 64.

Która grupa metryk w systemie CVSS odpowiada za cechy podatności, które są stałe w czasie oraz całkowicie niezależne od środowiska wdrożenia?

- Grupa metryk środowiskowych
- Grupa metryk czasowych
- **Grupa metryk bazowych**
- Grupa metryk telemetrycznych

# 66.

Jak nazywa się strategia reagowania na ryzyko, która polega na technicznym zmniejszeniu podatności, np. poprzez wdrożenie zapory ogniowej lub instalację poprawek?

- Unikanie ryzyka (Risk avoidance)
- **Redukcja ryzyka (Risk reduction)**
- Dzielenie ryzyka (Risk sharing)
- Retencja ryzyka (Risk retention)

# 67.

Na jakim porcie i przy użyciu jakiego protokołu domyślnie nasłuchują tradycyjne serwery Syslog?

- Port TCP 123
- **Port UDP 514**
- Port TCP 443
- Port UDP 123

# 68.

Które ulepszenie wprowadzone w standardzie syslog-ng (next generation) bezpośrednio zapobiega atakom typu Man-in-the-Middle oraz podsłuchiwaniu logów w sieci?

- Zastosowanie bezpołączeniowego transportu UDP.
- **Szyfrowanie TLS.**
- Wymuszenie stosowania kodów Facility od local0 do local7.
- Zastosowanie pasywnego DNS od Cisco Umbrella.

![[Pasted image 20260613201408.png]]
# 69.

W jakim celu atakujący najczęściej obierają za cel infrastrukturę protokołu NTP w sieci korporacyjnej?

- A. Aby przechwycić pliki sesji zrzutów narzędzia tcpdump.
- B. Aby wyłączyć filtrowanie URL oparte na reputacji w urządzeniach NGFW.
- **C. Aby sfałszować lub zakłócić informacje o czasie, co uniemożliwia późniejszą korelację logów z wielu maszyn podczas analizy incydentów.**
- D. Aby wymusić normalizację komunikatów w systemie SIEM.

# 70.

W jaki sposób złośliwe oprogramowanie (malware) wykorzystuje protokół DNS do eksfiltracji (wykradania) poufnych danych z sieci?

- Poprzez wstrzykiwanie ukrytych ramek iFrame do legalnych zapytań HTTP GET.
- **Poprzez kodowanie skradzionych danych w postaci długich subdomen w zapytaniach DNS kierowanych do kontrolowanego przez hakera serwera nazw.**
- Poprzez nadanie zapytaniom DNS kodu ważności Severity 0 (Emergency).
- Poprzez celowe fałszowanie flagi ESTABLISHED w pakietach TCP serwera DNS.

![[Pasted image 20260613201609.png]]
# 71.

Na czym polega technika ataku znana jako iFrame injection w protokole HTTP?

- Na sfałszowaniu źródłowego adresu IP w celu ominięcia bezstanowej listy ACL.
- **Na wstrzykiwaniu ukrytych ramek do legalnych witryn, które potajemnie przekierowują użytkownika do pobrania malware (Drive-by download).**
- Na obieraniu "warstw cebuli" w pakietach routowanych przez węzły sieci Tor.
- Na wysyłaniu pakietów ICMP w celu określenia systemu operacyjnego hosta.


# 72.

Dlaczego protokół HTTPS i stosowane w nim szyfrowanie SSL/TLS stanowi poważne wyzwanie dla analityków bezpieczeństwa w strukturach SOC?

- Ponieważ uniemożliwia ono nawiązywanie połączeń na portach niestandardowych.
- Ponieważ automatycznie blokuje ono działanie narzędzia tcpdump na hoście końcowym.
- **Ponieważ czyni dane HTTP całkowicie nieczytelnymi w tranzycie, uniemożliwiając systemom IDS/IPS inspekcję zawartości pakietów bez systemów deszyfrowania.**
- Ponieważ uniemożliwia ono identyfikację "Pacjenta Zero" w logach pocztowych.

# 74.

Dlaczego protokół ICMP jest chętnie wykorzystywany przez hakerów do ukradkowego wyprowadzania danych za pomocą tzw. tunelowania ICMP (ICMP tunneling)?

- Ponieważ ICMP automatycznie szyfruje dane przy użyciu protokołu SSL/TLS.
- **Ponieważ ruch ICMP wewnątrz sieci lokalnej jest często ignorowany lub rzadko filtrowany przez zapory sieciowe.**
- Ponieważ pakiety ICMP są domyślnie przetwarzane przez usługę Cisco Firepower AMP.
- Ponieważ ICMP nie posiada znacznika czasu, co uniemożliwia jego logowanie.

# 75.

Jaka jest główna słabość tradycyjnych, bezstanowych list kontroli dostępu (ACL)?

- Brak możliwości filtrowania pakietów na podstawie adresów IP.
- **Mogą zostać łatwo oszukane i ominięte m.in. przez IP spoofing, tunelowanie ruchu, użycie portów niestandardowych lub manipulację flagami TCP (np. ACK).**
- Wymagają wdrożenia dedykowanego serwera Syslog na porcie UDP 123.
- Nie potrafią logować zdarzeń typu Failure Audit.

# 77.

Co wchodzi w skład tzw. „piątki parametrów” (five-tuple) definiującej dane sesji (session data) w monitoringu sieci?

- Nazwa użytkownika, identyfikator sesji, adres MAC, kod Facility, znacznik czasu.
- **Źródłowy i docelowy adres IP, źródłowy i docelowy numer portu, kod używanego protokołu IP.**
- Adres URL, kategoria tematyczna, reputacja strony, typ błędu Windows, hash pliku.
- Identyfikator węzła Tor, klucz publiczny, klucz prywatny, certyfikat X.509, wersja TLS

![[Pasted image 20260613201909.png]]