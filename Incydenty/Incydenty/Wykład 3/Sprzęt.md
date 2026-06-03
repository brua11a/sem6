#### Firewall
1. Odporność na ataki sieciowe - do fierwalla nie można się włamać
2. Jedyny punkt tranzytowy - nie można wejść do sieci bez obejścia firewalla. Stwarza to problem z VPN, gdzie działanie site-to-site a point-to-point jest inne.
3. Wymuszanie polityki kontroli dostępu - nie można ustawić firewalla w tryb "przesyłaj wszystko".
4. Weryfikacja i oczyszczanie (sanityzacja) protokołów. Może polegać na sprawdzaniu długości ramki - jeśli jest za duża to może to oznaczać atak.
5. Urposzczenie zarządzania - za to w praktyce się płaci
6. Problem: konfiguracja - każda firma robi firewalle inaczej i każdego rozwiązania trzeba się nauczyć w praktyce od nowa.
7. Problem: aplikacje - są pewne aplikacje, np. VoIP, gdzie początek komunikacji zaczyna zawsze na tym samym porcie po czym skacze gdzieś indziej. Z perspektywy firewalla wygląda to jak zestawienie połączenia z zewnątrz.
8. Problem: obejście - użytkownicy mogą starac sie ominac zabezpieczenia bo ich wkurzają
9. Problem: spadek wydajności - analiza ruchu nie jest idealnie transparentna
10. Problem: ukrycie ruchu - cześć da się wysłać w postaci np. tunelowanej. 

###### Typy
- stateless: warstwa 3 i 4
- stateful: warstwa 3, 4, 5 - dochodzi warstwa sesji
- gateway: warstwa 3, 4, 5, 7 - dochodzi warstwa aplikacji, "rozumiany jest cały ruch" 
- NGFW - "łata luki", niby najlepsze rozwiązanie, uzupełnione poprzez IPS, "świadomość aplikacji", inteligentne ścieżki aktualizacji (bieżąca aktualizacja gdy pojawi się nowy exploit), ewolucja ochrony. Każdy producent robi po swojemu.

Należy też oczywiście zabezpieczyć hosta - firewall na hoście, transparentny (troche scam, ma obciążać jak najmniej), hybrydowy.

Tabelka jest na prezce.


#### IDS, IPS
Będzie o tym osobny wykład. W tych systemach leży cała analiza, najbardziej skomplikowane, zazwyczaj zewnętrzny sprzęt. Mogą też działać jako software na hoście, czasem się tak robi. Te systemy zawierają DPI - głęboka analiza pakietów, offline na kopii ruchu analizowanej na bieżąco. Nawet jeśli ktoś się dostał to głęboka analiza może zareagować po czasie.

IPS "działa od razu" ale wymaga, by caly ruch przez niego przechodził - narzut. IPS i IDS nie rozumieją ruchu zaszyfrowanego.

W sumie wiekszosc to powtorka z netsec