---
project_outline: "01-project-outline-sample"
---

# Elektromosautó-töltő hálózat relációs adatbázisának tervezése és teljesítményoptimalizálása AI támogatással

---
* Szerző: Hock Richárd
* Neptun: LWSKW4
* Témavezető: Lénárt Anett
* Projektazonosító: 2026-LA-01  
---

## Probléma

- **Skálázhatósági kihívások:** Az elektromosautó-töltő hálózatok nagy mennyiségű valós idejű és tranzakciós adatot generálnak (munkamenetek, mérések, időbélyegek).
- **Lassú lekérdezések:** Nagy adatmennyiség mellett az összetett analitikai lekérdezések (aggregációk, ablakfüggvények) indexelés nélkül drasztikus teljesítményromlást okoznak.
- **AI támogatás validációja:** Szükséges annak vizsgálata, hogy a generatív AI eszközök (LLM-ek) mennyire hatékonyak és megbízhatóak a relációs adatbázisok indexelési és lekérdezési optimalizációjában.

---

## Célfelhasználók

- **Adatbázis-fejlesztők:** Akik méretezhető és megfelelően normált (3NF) adatmodell-struktúrát terveznek.
- **Adatbázis-adminisztrátorok (DBA):** Akiknek feladata a teljesítmény optimalizálása, indexelési stratégiák kidolgozása és a rendszerstabilitás fenntartása.
- **Rendszerarchitektek & Kutatók:** Akik az AI-alapú kódgenerálás és adatbázis-optimalizáció korlátait és előnyeit értékelik ki.

---

## Tervezett hatókör

### Benne van a hatókörben
- **3NF Relációs Séma:** legalább 10 összekapcsolt tábla (Oracle / MS SQL Server).
- **Tesztadat-generálás:** 100 000+ töltési munkamenet és 1 000 000+ mérési rekord.
- **Összetett lekérdezések:** 10 komplex SQL lekérdezés és natív üzleti logika (PL/SQL / T-SQL).
- **Optimalizáció és AI:** Saját és AI által javasolt indexelési stratégiák (min. 3 lekérdezésnél) összehasonlító mérése végrehajtási tervek alapján.

### Nincs benne a hatókörben
- Komplett webes vagy mobil végfelhasználói GUI fejlesztése.
- Éles termelési (Production) környezet kiépítése.

---

## Kezdeti felhasználói utak

1. **Adatbázis-architektúra és feltöltés:**
   - Adatbázis-séma (DDL) inicializálása és hivatkozási integritás ellenőrzése.
   - Automatizált adatgeneráló szkript futtatása a milliós rekordtömeg betöltésére.

2. **Mérés és Teljesítményelemzés:**
   - Alapállapotú 10 összetett lekérdezés lefuttatása és kiinduló metrikák (EXPLAIN PLAN, I/O költség) rögzítése.
   - Saját indexek alkalmazása, majd a tesztek újrafuttatása.

3. **AI-alapú optimalizáció és összehasonlítás:**
   - A lekérdezések és a séma átadása az AI-nak optimalizálásra.
   - AI javaslatok manuális ellenőrzése, futtatása és a kapott teljesítménymetriák számszerű összevetése.

---

## Következő lépések

- Adatbázis-kezelő környezet (Oracle / MS SQL Server) és a DDL sématerv véglegesítése.
- A reprodukálható tesztadat-generáló szkript megírása (Python / Java).
- A 10 összetett SQL lekérdezés megfogalmazása és a mérésautomatizálási szkript elkészítése.
