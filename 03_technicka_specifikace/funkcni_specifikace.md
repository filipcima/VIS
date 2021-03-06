# Technická specifikace projektu
## Použité technologie
- C#, Python
- MongoDB 4.0
- REST API
- Desktopová aplikace: .NET Framework 4.5
- Webová aplikace: ASP.NET Framework
## Databáze
Objektová DB se hodí více, protože struktura dat bude různorodá.
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

## Údržba
Údržba bude probíhat v noci mezi 2:00-3:00. Automatické generování plánu bude probíhat v noci dne, který specifikuje nadřízený.

## Charakteristika uživatelů pracujících se systémem
Se systémem budou pracovat 3 typy uživatelů - __admin__, __zaměstnanec__, __nadřízený__.

__Zaměstnanec__ může zobrazit produkční plán, zobrazit plán svého nadřízeného, vytvořit osobní plán, upravit osobní plán, posílat žádosti o výměnu/smazání směny.

__Nadřízený__ může zobrazit seznam svých zaměstnanců, jejich plány. Vytvořit plán na následující období. Zobrazovat a upravovat produkční plán, schvaluje žádosti o smazání směny.

__Administrátor__ bude moci vytvářet uživatelské účty, provádět CRUD operace nad veškerými daty.

## Odhad maximální zátěže aplikace
S aplikací bude zároveň pracovat maximálně celkový počet uživatelů. Předpokládaná průměrná zátěž je 10-20% počtu uživatelů z celkového součtu. 

## Minimální požadavky
### Koncový zákazník - zaměstnanec, vedoucí zaměstnanec
- Intel Atom X5 Z8300 1,84 GHz
- 4GB DDR3, 32GB eMMC
- Windows 10 (64-bit)
### Databázový server 
- 1x vCPU up to 1,8 GHz
- 2 GB RAM, 32GB SSD
- OS Debian 8/Ubuntu 16.04
