Ticket trafia do osoby, która go musi zrozumieć - czy wymaga dalszego działania czy nie. To jest rola Tier 1. Jest to taka "sortownia" - co jest stałym atakiem (np. regularny DDoS o 5:00), a co jest anomalią. Tier 2 jest trochę wyżej, już wymaga kompetencji - incident responder. On dostaje tickety, które wymagają obsługi. Czasem schematyczne ("nowy atak typu fishing, co robimy?"), czasem mniej. Tier 3 proaktywnie szuka w sieci cyberzagrożeń.

SOC Manager chodzi od spotkania do spotkania i ma łączyć SOC z usługobiorcami. Zazwyczaj są to osoby z cyberbezpieczeństwa - muszą rzeczywiście rozumieć problem. 

Miedzy grupami nie ma skakania - z tieru 1 tylko do tieru 2, separation of duty. 

Sercem każdego SOC jest SIEM (Security Information and Event Managemwent). Wszystkie dane z czujników, eventy, są zamieniane w tickety. Logi są zcentralizowane, odfiltrowywane, wyliczane są statystyki, dopiero to się podaje dalej dzięki SIEM. 

SOAR (Security Orchestration, Automation and Response) pojawia się rzadziej. Orkiestracja - "dyrygent bierze wszystkie komponenty i nimi zarządza", zarządza się wejściami i wyjściami. Automatyzacja - jeśli coś jest nagminne, tworzy się playbook, czyli konkretne kroki do wykonania przy odpowiednich wydarzeniach. Response - "odpowiedź na coś". 

Metryki SOC "trzeba zapamiętać"
- dwell time - czas "dostępu", czas który osoba która nas atakuje może spędzic w naszej sieci zanim zdazymy zareagowac
- mean time to detect - jak szybko SOC reaguje
- mean time to respond - jak szybko SOC zatrzymuje atak
- mean time to contain - jak szybko SOC izoluje zagrożenie
- time to control - czas niezbędny na powtrzymanie propagacji złośliwego oprogramowania wewnątrz sieci, odzyskania zupełnej kontroli

Security vs Availability - bezpieczeństwo i dostępność trochę sobie zaprzeczają, podniesienie bezpieczeństwa obniża wygodę. Zasada dziewiątek - poziom dostępności 99.(9999)% ile czasu system ma działać. Dla systemów biurowych jest to 99.9% czyli 8h w roku. Maksymalne obostrzenia ma wojsko, lotnictwo, systemy kosmiczne - 30s. 