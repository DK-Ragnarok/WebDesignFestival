#festival web

## 1. Identita festivalu

| Položka | Specifikace |
|---|---|
| **Název** | Festival Temnoty 2 |
| **Ročník** | 2026 |
| **Lokalita** | Kutná Hora, Česká republika |
| **Datumový rozsah** | 10. 7. – 12. 7. 2026 (3 dny) |
| **Charakter festivalu** | Třídenní festival elektronické, alternativní a audiovizuální scény na dvou odlišných pódiích (open-air a kryté šapitó). |
| **Hlavní žánry/témata** | Post-Rock, Ambient, Indie Pop/Rock, Techno, experimentální elektronika. |

---

## 2. Účel webu

**K čemu web slouží:**
Jako hlavní digitální průvodce festivalem, který prezentuje všech 60 účinkujících, 3denní program a organizační pokyny pro areál Kutné hoře.

**Hlavní cíle webu:**
- Poskytnout přehledný časový harmonogram pro obě scény (Solar Horizon Stage a Lunar Forest Dome).
- Představit profily interpretů.
- Zprostředkovat praktické informace pro bezproblémový průběh návštěvy.

**Důležité akce uživatele na webu:**
- Zjištění času a scény, kde hraje vybraný interpret.
- Uložení vybraných vystoupení do osobního harmonogramu.
- Vyhledání pokynů k dopravě, orientaci v areálu a pravidlům festivalu.

---

## 3. Cílové skupiny

**1. Fanoušci alternativní a elektronické hudby (18–35 let)**
- **Potřeby:** Rychlý přístup k detailnímu line-upu, objevování nových jmen, osobní plánování.
- **Očekávání:** Rychlý, mobilně responzivní web pro snadné použití přímo pod pódiem.
- **Informace/funkce:** Interaktivní program s filtrem, uložení oblíbených interpretů.

**2. Běžní návštěvníci a místní (20–50 let)**
- **Potřeby:** Zjistit, jak a kdy se dostat do areálu, jaký je program na hlavním open-air pódiu.
- **Očekávání:** Srozumitelné, věcné a snadno dohledatelné praktické informace.
- **Informace/funkce:** Sekce "Praktické informace", přehledná navigace, informace o scénách.

---

## 4. Informační architektura

**Struktura webu / Sitemap:**
- `/` (Úvodní stránka)
- `/program` (Kompletní harmonogram)
    - `/program?den=1` (Pátek 10. 7.)
    - `/program?den=2` (Sobota 11. 7.)
    - `/program?den=3` (Neděle 12. 7.)
- `/ucinkujici` (Seznam 60 interpretů) -> `/ucinkujici/[id]` (Detail)
- `/sceny` (Seznam 2 scén) -> `/sceny/[id]` (Detail scény)
- `/prakticke-informace` (FAQ, doprava do Kutné hory)
- `/muj-program` (Interaktivní výběr vystoupení)

**Hlavní navigace:**
Úvod | Program | Účinkující | Scény | Praktické info | Můj program

**Vztahy mezi entitami:**
- Každé **Vystoupení** se odehrává na právě jedné **Scéně** (Solar Horizon nebo Lunar Forest).
- Každé **Vystoupení** patří právě jednomu **Účinkujícímu**.
- **Program** spojuje konkrétní čas, Účinkujícího a Scénu.

**Účel jednotlivých částí:**
- **Úvodní stránka:** Poutač, aktuální novinky.
- **Program:** Časová osa s možností filtrace podle 3 festivalových dnů a 2 scén.
- **Účinkující:** Katalog umělců (jméno, žánr, původ).
- **Scény:** Popis lokací (kapacita, typ stage).
- **Praktické informace:** Textový přehled o dopravě, ubytování a pravidlech.
- **Můj program (interaktivní část):** Osobní harmonogram, do kterého si uživatel přidává položky (data uložena přes LocalStorage prohlížeče).

---

## 5. Uživatelské scénáře

**Scénář 1: Zjištění programu na kryté scéně**
- **Typ uživatele:** Návštěvník v areálu.
- **Cíl:** Zjistit, kdo hraje dnes večer v Lunar Forest Dome.
- **Výchozí situace:** Začíná pršet, uživatel hledá přesun pod střechu a otevírá web na mobilu.
- **Očekávaný výsledek:** V menu vybere "Scény", klikne na "Lunar Forest Dome" a vidí chronologický program pro aktuální den s detaily vystupujících.

**Scénář 2: Sestavení osobního plánu na víkend**
- **Typ uživatele:** Fanoušek připravující se na festival.
- **Cíl:** Uložit si vybraná vystoupení, aby se vyhnul časovým kolizím mezi Solar a Lunar scénou.
- **Výchozí situace:** Uživatel sedí u počítače a prochází sekci "Program".
- **Očekávaný výsledek:** U každé kapely klikne na "Přidat do mého programu". V záložce "Můj program" pak vidí přehledný seznam vybraných koncertů ze všech 3 dnů.

**Scénář 3: Doprava do Kutné hory**
- **Typ uživatele:** Mimokutnhorský návštěvník.
- **Cíl:** Zjistit, jak se dostane do areálu.
- **Výchozí situace:** Uživatel stojí na nádraží v Kutné hoře.
- **Očekávaný výsledek:** Otevře sekci "Praktické info" a podle ní se vydá do arealu v Kutné hoře.

---

## 6. Použití AI

| Povinný bod k vysvětlení | Reflexe týmu |
|---|---|
| **K čemu jsme AI použili** | K reformátování struktury Markdown dokumentu a naplnění uživatelských scénářů a informační architektury přesně podle dodaných dat o festivalu Festival Temnoty  2 . Použili jsme již existující práci. |
| **Jak jsme výstup ověřili** | Zkontrolovali jsme, že specifikace odpovídá XML datům: 3 dny (10.-12. 7. 2026), 2 scény (Solar a Lunar), 60 umělců a že struktura dokumentu plní zadání. |
| **Co jsme přijali** | Čistou, zjednodušenou strukturu dokumentu a provázání scénářů s konkrétními názvy scén z databáze. |
| **Co jsme upravili nebo odmítnuli** | Přizpůsobili jsme popisky a cílové skupiny specifickému zaměření festivalu (elektronika, ambient), aby odpovídaly žánrům z XML souboru. |
| **Zjištěné limity a chyby** | Bylo nutné dávat pozor, aby AI nedomýšlela zbytečné funkce nad rámec jednoduché webové aplikace. |
