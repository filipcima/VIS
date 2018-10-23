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
    - plán na následující období vytvořený nadřízenym
- __user_plans__
    - plán vytvořen zaměstnancem na základě __superior_plan__
- __production_plans__
    - kolekce obsahující dokumenty s produkčním plánem
- __delete_requests__
    - chceme evidovat žádosti o zrušení směn, abychom mohli omezit žádosti na určity počet
- __change_requests__
    - kolekce, kde budou zaznamenány žádosti o změny
### Náročnost
Přibližná velikost jednoho dokumentu = 660 B

Přibližny počet dokumentů za měsíc u firmy s cca __32 zaměstnanci__:
- `users + admins = 40`
- `superior_plans = 2`
- `user_plans = 30`
- `production_plans = 2`
- `delete_requests + change_requests = 25`

Celkový přibližný stav za 1 měsíc: `99 * 660 B = 65 340 B ≈ 63.85 kB`.

Předpokládáme, že počet uživatelů se měnit nijak dramaticky nebude. Časem budou růst pouze kolekce __superior_plans__, __user_plans__, __production_plans__, __delete_requests__, __change_requests__ a to lineárně.

## Minimální požadavky
### Koncový zákazník
Intel Atom X5 Z8300 1,84 GHz

4GB DDR3, 32GB eMMC,

1xUSB 3.0, 3x USB 2.0, Gbit LAN, SD, Dual AC Wifi, BT 4.0, Audio out, HDMI 1.4, Mini DP,

Windows 10 (64-bit)
### Databázový server 
1x vCPU up to 1,8 GHz

2 GB RAM, 32GB SSD

OS Debian 8/Ubuntu 16.04
