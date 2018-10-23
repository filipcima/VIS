# Technická specifikace projektu
## Použité technologie
- C#, Python
- MongoDB 4.0
- REST API
- Desktopová aplikace: .NET Framework 4.5
- Webová aplikace: ASP.NET Framework
## Databáze
### Model
DB bude obsahovat následující dokumenty:
- __admins__
    - administrátorské účty
- __users__
    - kolekce pro zaměstnance a nadřízené
- __superior_plans__
    - plán na následující období vytvořen nadřízenym
- __user_plans__
    - plán vytvořen zaměstnancem na základě __superior_plan__
- __production_plans__
    - kolekce obsahující dokumenty s produkčním plánem
- __delete_requests__
    - chceme evidovat žádosti o zrušení směn, abychom mohli omezit žádosti na určity počet
- __change_requests__
    - kolekce, kde budou zaznamenány žádosti o změny
### Náročnost
Přibližná velikost jednoho dokumentu = 120 B

Přibližny počet dokumentů za měsíc
- `users + admins = 40`
- `superior_plans = 2`
- `user_plans = 30`
- `production_plans = 2`
- `delete_requests + change_requests = 25`

Celkovy přibližny narust za 1 měsíc: `99 * 120 B = 11 880 B = 11.6 kB`.
## Minimální požadavky
Mini počítač Intel Atom X5 Z8300 1,84 GHz
4GB DDR3, 32GB eMMC,
1xUSB 3.0, 3x USB 2.0, Gbit LAN, SD, Dual AC Wifi, BT 4.0, Audio out, HDMI 1.4, Mini DP,
Windows 10 (64-bit)