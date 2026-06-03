Port -> fizyczna dziura
Interface -> coś, po czym się komunikuje. Czasem można używać zamiennie, ale w wypadku interface wirtualnych, logicznych (np. loopback) należy je rozróżniać.

Zazwyczaj nie obchodzi nas struktura fizyczna, tylko topologia logiczna - adresacja, interface. To jest o wiele bardziej przydatne. SOHO co raz częściej się pojawia w firmach poprzez VPN - stwarza to problemy. 

Sieć LAN od WAN różni się przede wszystkim rozmiarem, przeznaczeniem i przepustowością. Co ciekawe, sieci LAN często będą szybsze, pomimo fizycznej infrastruktury. 

"Prawilny" model sieci to trójwarstwowy, hierarchiczny, gdzie zakres dostępu ("tam gdzie się podłącza"), część dystrybucyjna (kontrola sieci, ACL, zabezpieczenia, filtracje) oraz warstwa przesyłowa (szybki przesył bez filtrowania) są jasno rozdzielone. W małych firmach warstwę szkieletową i dystrybucyjną się integruje - Collapsed Core + warstwa dystrybucyjna. W takiej ifnrastrukturze przepustowość jest znacząco ograniczona, ale koszty też. 

Nie ma sieci bezpieczej bez firewalla, w różnych konfiguracjach. Historycznie:
1. Firewall typu sieć publiczna / sieć prywatna. Dzieli się urządzenia na sieć priv. i pub., z priv ruch idzie do pub., w drugą stronę nie. Będzie działać w sieciach blokujacych jakikolwiek dostęp z zewnątrz
2. Firewall z DMZ - wystawia się serwery na zewnątrz, do którego dozwala się dostęp z zewnątrz, z pub. Ta część jest najbardziej narażona na ataki, ale można ją lepiej, osobno zabezpieczyć. Strefa DMZ dla sieci priv. jest jak publiczna - blokuje sie ruch DMZ->priv. 
3. ZPF - zone based firewall. Zamiast rozróżniać wszystkie możliwości, porty przypisuje się do stref, po czym definiuje się zasady dla ruchu między strefami. W praktyce działa to jako ACL owinięte w wygodny wrapper.

