---
name: Jane Doe
neptun: ABC123
id: 2026-LG-02
github: https://github.com/example/ev-charging-db-optimization
github_project: https://github.com/users/username/projects/1
---
# Elektromosautó-töltő hálózat relációs adatbázisának tervezése és teljesítményoptimalizálása AI támogatással

A projekt egy elektromosautó-töltő hálózat robusztus relációs adatbázisának megtervezését, nagytömegű adatokkal történő feltöltését, valamint annak teljesítményoptimalizálását célozza meg AI támogatással. A fejlesztés során létrejön egy legalább 10 táblából álló, 3. normálformában lévő séma (Oracle vagy MS SQL Server alapon), melyet egy automatizált adatgeneráló szkript tölt fel több mint 100 000 töltési munkamenettel és 1 000 000 mérési rekorddal. A teljesítményelemzés 10 összetett SQL lekérdezés alapján történik, ahol a saját indexelési stratégiák mellett legalább 3 esetben AI által javasolt optimalizációk is kiértékelésre kerülnek.

## Célok

- **Elsődleges cél:** Egy megfelelően normált, nagymennyiségű tesztadattal feltöltött relációs adatbázis megtervezése és teljesítményének szisztematikus, mérésekkel alátámasztott optimalizálása (egyéni és AI által javasolt indexelési stratégiákkal).
- **Célfelhasználók / érintettek:** Adatbázis-fejlesztők, adatbázis-adminisztrátorok és teljesítményértékelést végző mérnökök.
- **Mérhető sikerkritériumok:** 
  - Legalább 10 táblából álló 3NF séma és hivatkozási integritás.
  - Sikeresen generált és betöltött 100 000+ munkamenet és 1 000 000+ állapotrekord.
  - 10 összetett SQL lekérdezés futási idejének és végrehajtási tervének dokumentált összehasonlítása az optimalizáció előtt és után.
  - Legalább 3 lekérdezés esetén az AI javaslatainak számszerűsített kiértékelése.
- **Korlátok:** Oracle Database vagy MS SQL Server használata; natív eljárások/triggerek (PL/SQL vagy T-SQL); külső AI modellek használatakor az adatvédelmi/biztonsági előírások betartása és az AI kódok kötelező manuális felülvizsgálata.

## Hatókör

### Benne van a hatókörben

- Relációs adatbázis-séma tervezése és megvalósítása (töltőállomások, pontok, felhasználók, járművek, foglalások stb.).
- Legalább egy tárolt eljárás, függvény vagy trigger megírása.
- Reprodukálható tesztadat-generáló szkript készítése.
- 10 összetett SQL lekérdezés (kapcsolások, aggregációk, ablakfüggvények, CTE-k) összeállítása.
- Szimpla, összetett és speciális indexek tervezése és tesztelése.
- AI-alapú lekérdezés-optimalizálási javaslatok lekérése (min. 3 lekérdezésre) és összehasonlító elemzése.
- Méréseket automatizáló és végrehajtási terveket (EXPLAIN PLAN / SET STATISTICS) rögzítő szkript.

### Nincs benne a hatókörben

- Teljes körű webes vagy mobil üzemeltetői felület (GUI) fejlesztése.
- Többjátékos vagy egyéb, nem adatbázis-fókuszú alkalmazásfunkciók.
- Éles termelési környezetbe történő automatikus CI/CD deployment.

## Jegyzetek

A tesztadat-generálás és a mérési folyamatok automatizálására tetszőleges nyelv (pl. Python vagy Java) használható. Mivel a hardveres erőforrások befolyásolhatják a futási időket, a méréseket többszörösen, átlagolással és a gyorsítótárak figyelembevételével kell elvégezni. Az AI javaslatait végrehajtás előtt mindig ellenőrizni és szükség esetén igazítani kell.