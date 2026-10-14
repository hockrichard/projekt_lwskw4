---
project_outline: "01-project-outline-sample"
---

# Elektromosautó-töltő hálózat relációs adatbázisának tervezése és teljesítményoptimalizálása AI támogatással

## 1. Szereplők és jogosultságok

| Szerep | Igény | Felelősség / hozzáférés |
| :---- | :---- | :---- |
| Adatbázis-fejlesztő | Relációs adatbázis tervezése, megvalósítása és optimalizálása. | Adatbázisséma létrehozása, tesztadat-generálás, SQL lekérdezések írása, teljesítményelemzés és indexelési stratégiák tesztelése. |
| AI Rendszer | Optimalizálási javaslatok készítése SQL lekérdezésekhez. | Adatbázis sémák és lekérdezések elemzése, indexelési és optimalizálási javaslatok generálása. |

## 2. Use case-ek / user storyk

### Adatbázis-tervezés és \-implementáció

- **Szereplő:** Adatbázis-fejlesztő  
- **Előfeltétel:** Megfelelő adatbázis-kezelő (Oracle vagy MS SQL Server) telepítése és konfigurálása.  
- **Fő folyamat:**  
  1. A fejlesztő megtervezi a legalább tíz táblát tartalmazó, harmadik normálformában lévő adatbázis-sémát.  
  2. Létrehozza a táblákat, kulcsokat és az integritási megszorításokat.  
  3. Létrehoz legalább egy tárolt eljárást vagy függvényt, illetve indokolt esetben triggert.  
- **Utófeltétel:** Működő, struktúrált és validált adatbázis jön létre.

### Tesztadat-generálás

- **Szereplő:** Adatbázis-fejlesztő  
- **Fő folyamat:**  
  1. A fejlesztő ír egy szkriptet vagy alkalmazáskomponenst, amely reprodukálható módon nagyszámú adatot generál.  
  2. Feltölti az adatbázist legalább 100 000 töltési munkamenettel és legalább 1 000 000 időbélyegzett mérési/állapotrekorddal.  
- **Utófeltétel:** Az adatbázis készen áll a teljesítménymérésekre.

### Teljesítményelemzés és optimalizálás

- **Szereplő:** Adatbázis-fejlesztő, AI rendszer  
- **Fő folyamat:**  
  1. A fejlesztő elkészít 10 összetett SQL lekérdezést (kapcsolások, aggregációk, ablakfüggvények stb.).  
  2. Lefuttatja a lekérdezéseket optimalizálás nélkül, és rögzíti a végrehajtási terveket és a futási jellemzőket.  
  3. Indexeket és optimalizációkat tervez és alkalmaz (szimpla, összetett és speciális indexek).  
  4. Legalább 3 lekérdezés esetén kikéri az AI rendszer optimalizálási javaslatait.  
  5. Lefuttatja az optimalizált és az AI által javasolt lekérdezéseket.  
  6. Számszerűen összehasonlítja és értékeli a kapott eredményeket.  
- **Alternatív / hibafolyamatok:**  
  - Ha az AI által javasolt SQL hibás vagy végrehajthatatlan, a fejlesztő manuálisan javítja, és dokumentálja a hibát.  
- **Utófeltétel:** Dokumentált összehasonlító elemzés a különböző optimalizációs megközelítésekről és indexelési stratégiákról.

## 3. Funkcionális követelmények

| Követelmény | Elfogadási kritérium | Prioritás |
| :---- | :---- | :---- |
| Relációs adatbázisséma. | Az adatmodell legalább 10 egymással kapcsolatban álló táblából áll (töltőállomások, pontok, felhasználók, járművek, foglalások stb.), és legalább 3\. normálformában van. A hivatkozási integritás biztosított. | Kötelező |
| Tesztadat-generálás. | Reprodukálható módon létrejön legalább 100 000 töltési munkamenet és 1 000 000 állapotrekord. | Kötelező |
| Összetett SQL lekérdezések. | Elkészül 10 lekérdezés, amelyek tartalmaznak többtáblás kapcsolást, aggregációt, időintervallum-keresést, részlekérdezést/CTE-t és ablakfüggvényt. | Kötelező |
| Indexelés. | Egyszerű, összetett és speciális (függvényalapú vagy szűrt) indexek tervezése, létrehozása és tesztelése. | Kötelező |
| Tárolt eljárás / függvény. | Legalább egy tárolt eljárás, függvény vagy trigger megvalósítása a választott rendszer natív nyelvén (PL/SQL vagy T-SQL). | Kötelező |
| Mérési szkript. | Elkészül egy automatizált eszköz vagy szkript az optimalizálás előtti és utáni eredmények reprodukálható összehasonlítására. | Kötelező |
| AI támogatás integrációja. | Az AI rendszer legalább 3 lekérdezéshez ad indexelési vagy optimalizációs javaslatot. | Kötelező |

Prioritás: **Kötelező** \= a végtermékhez szükséges; **Ajánlott** \= fontos; **Lehetséges** \= idő esetén opcionális (pl. particionálás vizsgálata).

## 4. Üzleti szabályok és korlátok

| Szabály vagy korlát | Indoklás |
| :---- | :---- |
| Az adatbázisnak Oracle vagy MS SQL Server rendszert kell használnia. | Ez a két rendszer biztosítja a feladathoz szükséges natív teljesítményelemző eszközöket és speciális indexelési lehetőségeket. |
| A kulcsokat és hivatkozási integritásokat adatbázis szinten kell érvényesíteni. | Az adatkonzisztencia fenntartása érdekében elengedhetetlen. |
| Az AI által generált utasítások (SQL, DDL, PL/SQL, T-SQL) nem hajthatók végre ellenőrzés nélkül. | Biztonsági és stabilitási okokból a kód felülvizsgálata szükséges. |
| A külső AI szolgáltatás használatakor be kell tartani az adatvédelmi és biztonsági korlátokat. | Szenzitív vagy üzleti titkot képező (még ha szimulált is) adat ne kerüljön nyilvános LLM modellekbe kontrollálatlanul. |
| A projekt nem követeli meg teljes üzemeltetői webalkalmazás fejlesztését. | A fókusz a relációs adatbázis tervezésén és a teljesítményoptimalizáláson van. |

## 5. Felhasználói felület és munkafolyamat

Mivel a projekt egy adatbázis backend fókuszú feladat, nincs hagyományos végfelhasználói GUI (webes felület) megkövetelve. A "munkafolyamat" az adatbázis-fejlesztő szemszögéből az adatbázis-kezelő (pl. SQL Developer, SSMS) és a mérési szkriptek, terminálok használatát jelenti. Opcionálisan egy nagyon egyszerű üzemeltetői monitorozó felület készíthető a lekérdezések eredményeinek megjelenítésére, de ez csak lehetséges bővítés.

## 6. Nem funkcionális követelmények

| Követelmény | Ellenőrzés módja |
| :---- | :---- |
| Adatmodell minősége. | A séma ellenőrzése a harmadik normálforma (3NF) és a kötelező entitások (állomások, munkamenetek stb.) megléte szempontjából. |
| Reprodukálhatóság. | A tesztadat-generáló és a mérési szkriptek többszöri, azonos eredménnyel záruló futtatása üres adatbázison. |
| Teljesítményelemzés mélysége. | Az EXPLAIN PLAN, DBMS\_XPLAN (Oracle) vagy az Actual Execution Plan, SET STATISTICS (MS SQL) által generált végrehajtási tervek és futási idők részletes dokumentációja legalább 5 lekérdezésre. |
| AI összehasonlítás. | A hallgató saját és az AI által javasolt optimalizációinak (3 lekérdezésnél) helyességének, végrehajthatóságának és mért teljesítményének kvantitatív összevetése. |
| Biztonság és adatvédelem | Rövid dokumentáció a külső AI eszköz használatának biztonsági kockázatairól és azok kezeléséről. |

## 7. Nyitott kérdések és kockázatok

| Kérdés / kockázat | Hatás | Felelős | Feloldás / döntés |
| :---- | :---- | :---- | :---- |
| Milyen programozási nyelven íródjon a tesztadat-generátor és a mérési szkript? | Befolyásolja a fejlesztési sebességet és a reprodukálhatóságot. | Hallgató | Szabadon választott (pl. Python, Java). |
| Az AI szolgáltatás hibás optimalizálási javaslatot ad. | Az AI-alapú optimalizáció mérési eredményei nem lesznek relevánsak. | Hallgató | Az AI javaslatainak manuális ellenőrzése futtatás előtt, hibák esetén dokumentálás és iteratív javítás. |
| A hardveres erőforrások korlátai (pl. kevés RAM vagy lassú SSD) torzíthatják a teljesítménymérést. | A nagy (1M+) adatbázison futó lekérdezések futási ideje változhat. | Hallgató | A mérések többszöri (pl. 3x-5x) lefuttatása, átlagolás, cache-ek ürítése (vagy annak figyelembevétele) a mérések között. |

## 8. Kezdeti technikai javaslat

### Javasolt megoldás

A rendszer alapja egy Oracle Database vagy Microsoft SQL Server adatbázis-kezelő. Az adatbázis és a táblák létrehozása DDL szkriptekkel, az üzleti logika (pl. foglalások ellenőrzése) PL/SQL vagy T-SQL eljárásokkal/triggerekkel történik. A nagytömegű tesztadatokat egy Python (pl. Faker és SQLAlchemy könyvtárak) vagy Java alkalmazás generálja. A teljesítménymérést egy saját készítésű szkript végzi, amely lefuttatja az SQL fájlokat, és összegyűjti az adatbázis motor által biztosított (EXPLAIN PLAN, STATISTICS IO) metrikákat. Az optimalizáció során a DDL (indexek) és a DML (lekérdezések) iteratív módosításon és AI alapú felülvizsgálaton esik át.

### Technológiai irány

| Terület | Jelölt technológia / megközelítés | Megfontolás oka |
| :---- | :---- | :---- |
| Adatbázis | Oracle Database vagy Microsoft SQL Server | A projekt követelménye, biztosítják a robusztus teljesítményelemző eszközöket és az összetett indexelési lehetőségeket. |
| Adatbázis nyelv | SQL \+ PL/SQL (Oracle) vagy T-SQL (MS SQL) | Natív eljárások, függvények, triggerek megírásához. |
| Adatgenerálás & Mérés | Python, Java, bash vagy natív adatbázis szkript | Megfelelő a nagytömegű adat generálásához, az API hívásokhoz és a mérések automatizálásához. |
| AI Asszisztens | OpenAI API (ChatGPT), Anthropic Claude, vagy Google Gemini | A lekérdezés-optimalizálási javaslatok lekéréséhez a 3 kötelező esetben. |
| Teljesítményeszközök | DBMS\_XPLAN / SQL Trace (Oracle), vagy Actual Execution Plan / SET STATISTICS (MS SQL) | Kötelező, beépített eszközök a végrehajtási tervek lekéréséhez. |

### Kezdeti architektúravázlat

```mermaid
flowchart LR
    DEV[Fejlesztő] --> DB[Relációs adatbázis]
    DB --> SC[Adatgeneráló szkript]
    SC --> SQL[SQL lekérdezések]
    SQL --> AI[AI optimalizálás]
    AI --> OP[Optimalizált SQL]
    OP --> CMP[(Új metrikák, összehasonlítás)]
```

## 9. Megvalósíthatóság és technikai kockázatok

| Kockázat / feltételezés | A 2. félévre tervezett validáció | Tartalék megközelítés |
| :---- | :---- | :---- |
| Az adatbázis-motor megfelelő beépített metrikákat (pl. I/O költség) szolgáltat a mérésekhez. | A natív eszközök (pl. DBMS\_XPLAN, SET STATISTICS IO) kipróbálása egy kisebb mintatáblán a fejlesztés elején. | Szükség esetén az OS szintű metrikák bevonása vagy más mérésiadat-gyűjtési módszer keresése. |
| Az 1 000 000+ rekord generálása és betöltése nem okoz extrém teljesítmény- vagy helyproblémát. | A kötegelt (batch) beszúrás (pl. bulk insert) használata a soronkénti helyett, és az adatbázis növekedésének monitorozása. | Kisebb adatbázisfájl-növekmény beállítása, és a szkript futtatásának részekre bontása. |
| Az AI által biztosított megoldás használható a választott relációsadatbázis-kezelő rendszerhez. | Az LLM promptolása során specifikálni kell a pontos rendszert (pl. "Oracle 19c-hez javasolj indexet"). | Az AI javaslatainak manuális fordítása/szintaktikai javítása a hallgató által. |
| A teljesítménykülönbség észrevehető lesz az indexek használatával. | Olyan (rosszul optimalizált, nagy adatmennyiséget mozgató) lekérdezések szándékos írása a kiindulási állapotban, amelyeknél az indexek garantáltan drasztikus javulást eredményeznek. | A tesztadatok számának és a lekérdezések bonyolultságának növelése, amíg a különbség mérhető nem lesz. |

