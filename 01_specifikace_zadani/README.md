# Plánování směn v restauracích/kavárnách - vize systému
## Co?
Cílem projektu je implementovat systém pro plánování směn v kavárnách/restauracích nebo v podobných zařízeních, kde se na jedné pozici střídá více lidí.
## Jak?
Do databáze budou zaměstnanci před začátkem každého měsíce vyplňovat, kdy mají volno na následující období a vedoucí do systému zadá plán směn. Aplikace pak na základě dat z databáze bude sama schopna rozdělit rovnoměrně práci mezi zaměstnance, vytvoří statistiky, které budou mít k nahlédnutí jak zaměstnanci, tak lidé z vedení.
## Kde?
Veškerá data budou uložena v databázi, takže k nim budou uživatelé moci přistupovat pomocí webové nebo desktopové aplikace.
## Kdo?
Se systémem budou pracovat 2 skupiny lidí - __zaměstnanci__ a jejich __nadržízení__.
### Zaměstnanci budou pracovat s aplikací/systémem následovně:
- Zjistí si, kdy mají další směny
- Zjistí, kolik hodin mají odpracováno
- Budou žádat o změny směn
- Budou plánovat, kdy mají čas na další období
### Vedoucí zaměstnanci (nadřízení) budou:
- Zadávat plán směn na následující období
- Kontrolovat počty odpracovaných hodin zaměstnanců
- Schvalovat žádosti o zrušení účasti na směně
## Proč?
Systém chceme implementovat, abychom zjednodušili plánování směn na následující období (např. měsíc). Vedoucí obsluhy nebude muset ručně prohlížet, který zaměstnanec má kdy volno, jelikož systém automaticky vyhodnotí, kdo bude kdy pracovat a spravedlivě rozdělí počet hodin za období. Další funkcionalitou bude žádost o výměnu směn, kde ostatním, kteří měli v daném termínu čas, přijde upozornění nebo email s žádostí o výměnu směny.
