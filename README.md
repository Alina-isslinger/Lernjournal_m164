## Was ist SQL?

SQL (Structured Query Language) ist eine Sprache, um mit Datenbanken zu arbeiten.  
Man kann damit Daten speichern, abfragen, ändern und löschen – unabhängig davon, welches Datenbanksystem verwendet wird.

## Wofür wird SQL genutzt?

- **Struktur festlegen** (z. B. Tabellen erstellen)
- **Daten abfragen** (z. B. mit `SELECT`)
- **Daten bearbeiten** (z. B. `INSERT`, `UPDATE`, `DELETE`)
- **Transaktionen steuern** (z. B. `COMMIT`, `ROLLBACK`)
- **Zugriffsrechte verwalten** (z. B. `GRANT`, `REVOKE`)

# Aufgaben
# Tag 1
#### Was ich gemacht habe
Zuerst habe ich eine Einführung in Datenbanken bekommen und dabei wichtige Begriffe wie Tabelle, Datenbank, Primärschlüssel und Fremdschlüssel wiederholt. So konnte ich mein Wissen auffrischen.
Danach habe ich wiederholt, wie man Daten normalisiert. Das heisst, ich habe Daten so umgebaut, dass sie gut strukturiert sind und keine doppelten Informationen enthalten. Ich habe dabei die 1., 2. und 3. Normalform wiederholz und ein Beispiel mit einem Tourenplaner durchgearbeitet.
Um praktisch arbeiten zu können, habe ich verschiedene Programme und Tools installiert, mit denen man mit Datenbanken arbeitet:
- **XAMPP** für MariaDB auf dem eigenen Computer    
- **MySQL Workbench**, ein Programm zum Zeichnen von Datenmodellen und Schreiben von SQL-Befehlen
Ausserdem habe ich ein Entity-Relationship-Modell (ERM) erstellt. Das zeigt, wie die Tabellen in der Datenbank miteinander verbunden sind. Daraus habe ich dann ein Entity-Relationship-Diagramm (ERD) gezeichnet, das hilft, die Struktur besser zu verstehen.
Am Ende haben wir nochmal alles wiederholt, um den Stoff zu festigen.
#### Bsp. einer Aufgabe, welche ich gelöst habe:
- **3. Normalform (3NF)**:
#### 1. **Zusammenfassung in Stichworten**
- 3 Phasen: konzeptionell (ERM), logisch (ERD), physisch
- Unterschiedliche Datenmodelle je nach Einsatzzweck
- Normalisierung wichtig für Datenkonsistenz und -struktur
- Unterschiedliche Modellierungen je nach Systemtyp (operativ vs. analytisch)
#### 2. **Normalisierungsschritte wiederholen**
Schreiben Sie die Schritte zur Normalisierung (bis zur 3. Normalform) in Ihr Lernportfolio:
1. **1. Normalform (1NF)**:  
   - Nur atomare Werte (keine Mehrfachwerte oder Listen in Zellen)
2. **2. Normalform (2NF)**:  
   - Tabelle ist in 1NF  
   - Alle Nicht-Schlüsselattribute hängen vollständig vom Primärschlüssel ab
3. **3. Normalform (3NF)**:  
   - Tabelle ist in 2NF  
   - Keine transitive Abhängigkeit (Nicht-Schlüsselattribute hängen nur vom Primärschlüssel ab)
#### 3. **Aufgabe 'Tourenplaner' bearbeiten**
- ERM (konzeptionelles Modell) habe ich von Hand skizziert
- ERD (logisches Modell) in MySQL Workbench umsetzt
- Normalisierungsschritte angewendet, um saubere Tabellenstrukturen zu erstellen

# Tag 2
Theorie-Zusammenfassung
- In datenbankgestützten Informationssystemen werden Attribute Entitätstypen zugeordnet.
- Problem: Redundanz, wenn mehrere Entitätstypen dieselben Attribute besitzen (z. B. Mitarbeiter auch Kunde).
- Lösung: Generalisierung – gemeinsame Attribute werden in einem übergeordneten Entitätstyp gespeichert.
- Die spezialisierten Entitäten (z. B. Kunde, Fahrer) enthalten nur noch ihre spezifischen Attribute.
- Die Beziehung zwischen Spezialisierung und Generalisierung wird als „is_a“-Beziehung bezeichnet.
- Wichtig: Jede Spezialisierung verweist per Fremdschlüssel auf den generalisierten Entitätstyp.
- Ähnlich wie Vererbung in der objektorientierten Programmierung.
### Eigenes Beispiel für eine Generalisierung
- Allgemeiner Entitätstyp: `Person`
- Spezialisierungen:
  - `Lehrer` (zusätzliche Attribute: Fächer, Schulstufe)
  - `Schüler` (zusätzliche Attribute: Klasse, Notendurchschnitt)
### Beispiele von Klassenkamerad:innen
- `Fahrzeug` → `Auto`, `Motorrad`
- `Gebäude` → `Wohnhaus`, `Bürogebäude`
- `Produkt` → `Lebensmittel`, `Elektronikgerät`
## Identifying vs. Non-Identifying Relationship
### Theorie-Zusammenfassung
#### Identifying Relationship
- Der Fremdschlüssel ist Teil des Primärschlüssels der Child-Tabelle.
- Die Child-Entität ist abhängig von der Parent-Entität.
- Beispiel: `Gebäude` – `Raum`  
  → Ein Raum ist nur in einem Gebäude eindeutig.
#### Non-Identifying Relationship
- Der Fremdschlüssel ist NICHT Teil des Primärschlüssels.
- Die Beziehung ist loser – Änderungen möglich, ohne Identität zu beeinflussen.
- Beispiel: `Mitarbeiter` – `Abteilung`  
  → Ein Mitarbeiter kann die Abteilung wechseln, bleibt aber dieselbe Person.
### Eigenes Beispiel für Identifying Relationship
- `Bestellung` – `Bestellposition`  
  → `Bestellposition` wird durch `Bestellnummer + Positionsnummer` identifiziert  
  → `Bestellnummer` ist Teil des Primärschlüssels
### Beispiele von Klassenkamerad:innen
- `Buch` – `Kapitel`
- `Rechnung` – `Rechnungszeile`
- `Turnier` – `Spiel`
### Anwendungsfälle (Recherche mit ChatGPT/Phind)
- Identifying:
  - Wenn ein untergeordnetes Objekt **ohne das übergeordnete nicht existieren kann**
  - Häufig bei **hierarchischen Strukturen**, z. B. Dateisystem (Ordner – Datei)
- Non-Identifying:
  - Wenn untergeordnete Entitäten **eigenständig sind**
  - Typisch bei Zuweisungen: z. B. Mitarbeiter → Projekt, Schüler → Kurs
  # Zusammenfassung: Datenbanksysteme (DBS / DBMS)
## 1. Was ist ein Datenbanksystem?
- **Datenbanksystem (DBS)** = Datenbank + Verwaltungssoftware (DBMS)
- **DBMS (Database Management System)**: Software zur Verwaltung, Sicherung und Organisation von Daten
- **Datenbank (DB)**: Der eigentliche, dauerhaft gespeicherte Datenbestand
## 2. Hauptfunktionen eines DBMS
### Zentrale Datenhaltung
- Einheitliche Ablage aller Daten
- Keine redundante Speicherung
- Strukturierte Verknüpfung der Daten (Beziehungen)
### Datenbanksprache
- **DQL (SELECT)**: Daten abfragen
- **DDL (CREATE, ALTER, DROP)**: Datenstruktur definieren
- **DML (INSERT, UPDATE, DELETE)**: Daten ändern
- **DCL (GRANT, REVOKE)**: Rechteverwaltung
- **TCL (COMMIT, ROLLBACK)**: Transaktionssteuerung
### Katalog (Data Dictionary)
- Enthält Metadaten über Tabellen, Spalten, Beziehungen und Regeln
### Benutzersichten (Views)
- Angepasste Datenansicht für unterschiedliche Nutzergruppen
### Konsistenz- und Integritätskontrolle
- Logische Prüfungen (Constraints)
- Physikalische Integrität (Speicherstruktur)
### Zugriffskontrolle
- Benutzer- und Rollenrechte
- Schutz auf Tabellen-, Spalten- und Sichtenebene
### Transaktionen & ACID-Prinzip
- **A**tomarität
- **C**onsistenz
- **I**solation
- **D**auerhaftigkeit
- Sperr- und Synchronisationsmechanismen
### Datensicherung & Wiederherstellung
- Backup, Journaling, Crash-Recovery
## 3. Vorteile eines DBMS
- Standardisierte Datenformate und -namen
- Effiziente Speicherung und schnelle Abfragen
- Reduzierter Entwicklungsaufwand
- Hohe Flexibilität und Datenunabhängigkeit
- Gleichzeitiger Zugriff durch mehrere Benutzer
- Zentrale Verwaltung senkt Betriebskosten
## 4. Nachteile eines DBMS
- Hohe Kosten für Anschaffung, Wartung und Betrieb
- Leistungseinbußen bei speziellen Aufgaben
- Komplexität erfordert geschultes Personal
- Sicherheits- und Synchronisationsaufwand
- Single Point of Failure (Gegenmaßnahme: verteilte Systeme)
## 5. Wann reichen einfache Dateien?
- Kein Mehrbenutzerzugriff notwendig
- Feste, einfache und unveränderliche Datenstrukturen
- Strenge Echtzeitanforderungen
- Beispiel: Log-Dateien, einfache Konfigurationsdaten
## 6. DBMS-Ranking (Stand: April 2025)
| DBMS           | Hersteller     | Top 10 Platzierung |
|----------------|----------------|---------------------|
| Oracle         | Oracle         | Platz 1             |
| MySQL          | MySQL AB       | Platz 2             |
| MS SQL Server  | Microsoft      | Platz 3             |
| PostgreSQL     | –              | Platz 4             |
| IBM Db2        | IBM            | Platz 9             |
## DDL Aufgabe:
CREATE SCHEMA IF NOT EXISTS `AufgabenDB`
  DEFAULT CHARACTER SET utf8mb4
  COLLATE utf8mb4_unicode_ci;

USE `AufgabenDB`;

CREATE TABLE `tbl_fahrer` (
  `ID` INT NOT NULL AUTO_INCREMENT,
  `Name` VARCHAR(45) NOT NULL,
  `Vorname` VARCHAR(45) NOT NULL,
  `Telefonnummer` VARCHAR(45),
  PRIMARY KEY (`ID`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

CREATE TABLE `tbl_disponent` (
  `ID` INT NOT NULL AUTO_INCREMENT,
  `Name` VARCHAR(45) NOT NULL,
  `Vorname` VARCHAR(45) NOT NULL,
  `Telefonnummer` VARCHAR(45),
  PRIMARY KEY (`ID`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

DROP TABLE IF EXISTS `tbl_disponent`;

CREATE TABLE `tbl_disponent` (
  `ID` INT NOT NULL AUTO_INCREMENT,
  `Name` VARCHAR(45) NOT NULL,
  `Vorname` VARCHAR(45) NOT NULL,
  `Telefonnummer` VARCHAR(45),
  PRIMARY KEY (`ID`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

CREATE TABLE `tbl_Mitarbeiter` (
  `MA_ID` INT NOT NULL AUTO_INCREMENT,
  `Name` VARCHAR(50) NOT NULL,
  `Vorname` VARCHAR(30) NOT NULL,
  `Geburtsdatum` DATETIME,
  `Telefonnummer` VARCHAR(12),
  `Einkommen` FLOAT(10,2),
  PRIMARY KEY (`MA_ID`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

ALTER TABLE `tbl_Mitarbeiter`
  MODIFY `Name` VARCHAR(50) CHARACTER SET latin1 NOT NULL,
  MODIFY `Vorname` VARCHAR(30) CHARACTER SET latin1 NOT NULL;

ALTER TABLE `tbl_fahrer`
  DROP COLUMN `Name`,
  DROP COLUMN `Vorname`,
  DROP COLUMN `Telefonnummer`;

ALTER TABLE `tbl_disponent`
  DROP COLUMN `Name`,
  DROP COLUMN `Vorname`,
  DROP COLUMN `Telefonnummer`;

ALTER TABLE `tbl_fahrer`
  ADD COLUMN `MA_ID` INT NOT NULL,
  ADD CONSTRAINT `FK_fahrer_mitarbeiter`
    FOREIGN KEY (`MA_ID`) REFERENCES `tbl_Mitarbeiter`(`MA_ID`);

ALTER TABLE `tbl_disponent`
  ADD COLUMN `MA_ID` INT NOT NULL,
  ADD CONSTRAINT `FK_disponent_mitarbeiter`
    FOREIGN KEY (`MA_ID`) REFERENCES `tbl_Mitarbeiter`(`MA_ID`);
# Tag 3
## Repetition M162 Datentypen
## Datentypen in MariaDB (MySQL)

| Datentyp                                | MariaDB (MySQL)               | Beispiel           | Bemerkung / Einstellungen         |
|-----------------------------------------|-------------------------------|--------------------|-----------------------------------|
| Ganze Zahlen                            | INT                           | 1234               |                                   |
| Natürliche Zahlen                       | UNSIGNED INT                  | 1234               | Positive ganze Zahlen            |
| Festkommazahlen (Dezimalzahlen)         | DECIMAL(M,D)                  | DECIMAL(6,2) 1234.56| M = Gesamte Anzahl Stellen, D = Nachkommastellen |
| Aufzählungstypen                        | ENUM('Wert1', 'Wert2', ...)   | ENUM('rot', 'blau')| Aufzählung von Werten            |
| Boolean (logische Werte)               | BOOLEAN / TINYINT(1)           | TRUE               | 1 = TRUE, 0 = FALSE              |
| Zeichen (einzelnes Zeichen)            | CHAR(1)                       | 'A'                | Einzelnes Zeichen                |
| Gleitkommazahlen                       | FLOAT, DOUBLE                 | 12.34              |                                   |
| Zeichenkette fester Länge              | CHAR(M)                       | 'Beispiel'         | Feste Länge                      |
| Zeichenkette variabler Länge           | VARCHAR(M)                    | 'Beispiel'         | Variable Länge                   |
| Datum und/oder Zeit                    | DATE, DATETIME, TIME           | '2025-05-06'       |                                   |
| Zeitstempel                             | TIMESTAMP                     | '2025-05-06 10:00:00' | Automatisch mit Speicherung des aktuellen Zeitstempels |
| Binäre Datenobjekte variabler Länge    | BLOB                          | NULL               | z.B. für Bilder                  |
| Verbund                                 | SET                           | SET('rot', 'blau') | Menge von Werten                 |
| JSON                                    | JSON                          | '{"name": "Test"}' | Speicherung von JSON-Daten       |

### Mehrfachbeziehungen
Bei Mehrfachbeziehungen haben zwei Tabellen mehrere Beziehungen, die unabhängig voneinander sind und jeweils einen anderen Sachverhalt repräsentieren. Um die verschiedenen Beziehungen eindeutig zu kennzeichnen, müssen sie möglichst aussagekräftig beschriftet werden (Rolle). Die Kardinalitäten können natürlich verschieden sein, da die Beziehungen voneinander unabhängig sind. In den Beispielen unten gibt es drei unabhängige Beziehungen zwischen den Entitätstypen `tbl_Fahrten` und `tbl_Orte`. Eine dieser Beziehungen ist die Auflistung der Orte, die bei einer Tour angefahren werden können. Dies ist eine mc:mc-Beziehung und benötigt daher eine Transformationstabelle.
### Rekursion (strenge Hierarchie)
Bei einer Rekursion handelt es sich um eine Beziehung, bei der ein Entitätstyp mit sich selbst in Beziehung steht. Dies tritt oft in Hierarchien auf, z.B. bei einer Unternehmensstruktur, wo jeder Mitarbeiter genau einen Vorgesetzten hat. Eine reine Hierarchie kann innerhalb der gleichen Tabelle abgebildet werden. Sie erhält einen Fremdschlüssel, der auf den Identifikationsschlüssel der eigenen Tabelle verweist.
### Einfache Hierarchie (mit Zwischentabelle)
Wenn mehrere Oberelemente zugelassen sind (z. B. mehrere Projektleiter), handelt es sich um eine mc:mc-Beziehung, die eine Transformationstabelle benötigt. Die beiden Fremdschlüssel der Transformationstabelle zeigen jeweils auf einen Identifikationsschlüssel der gleichen Tabelle, jedoch in unterschiedlichen Rollen.
### Stücklistenproblem
Eine klassische Anwendung der Rekursion in der Datenmodellierung ist die Stücklistenproblematik. Bei modularen Produkten, die sich aus mehreren Einzelteilen zusammensetzen, wird eine Tabelle benötigt, die angibt, welche Teile in welchem Produkt enthalten sind. Diese Beziehung muss rekursiv dargestellt werden, um die Bauteile auf die elementare Ebene herunterzubrechen.
### SQL Code für Mehrfachbeziehungen und Rekursion
^^```sql
CREATE TABLE tbl_Fahrten_Orte (
    FahrtID INT,
    OrtID INT,
    Rolle VARCHAR(255), -
    PRIMARY KEY (FahrtID, OrtID)
);
CREATE TABLE tbl_Mitarbeiter (
    ID INT PRIMARY KEY,
    Vorname VARCHAR(100),
    Nachname VARCHAR(100),
    FS_Vorgesetzter INT,  
    FOREIGN KEY (FS_Vorgesetzter) REFERENCES tbl_Mitarbeiter(ID)
);
### Insert into
````sql 
INSERT INTO customers
VALUES (NULL, 'Heinrich', 'Schmitt', 2, 'Zürich');
INSERT INTO customers
VALUES (NULL, 'Sabine', 'Müller', 2, 'Bern');
INSERT INTO customers
VALUES (NULL, 'Markus', 'Mustermann', 1, 'Wien');
INSERT INTO customers (first_name, last_name)
VALUES ('Herr', 'Maier');
INSERT INTO customers (first_name, last_name, country_id, city)
VALUES ('Herr', 'Bulgur', 2, 'Sirnach');
INSERT INTO customers (first_name, last_name)
VALUES ('Maria', 'Manta');
INSERT INTO customers (last_name, city, country_id)
VALUES ('Fesenkampp', 'Duisburg', 3);
INSERT INTO customers (first_name)
VALUES ('Herbert');
INSERT INTO customers (last_name, first_name, city, country_id)
VALUES ('Schulter', 'Albert', 'Duisburg', 4);
INSERT INTO customers (first_name, last_name, country_id, city)
VALUES ('Brunhild', 'Sulcher', 1, 'Süderstade');
INSERT INTO customers
VALUES (NULL, 'Jochen', 'Schmied', 2, 'Solingen');
INSERT INTO customers
VALUES (NULL, '', 'Doppelbrecher', 2, NULL);
INSERT INTO customers (last_name, city, country_id)
VALUES ('Christoph', 'Fesenkampp', 3);
INSERT INTO customers (first_name)
VALUES ('Herbert');
INSERT INTO customers (last_name, first_name, city, country_id)
VALUES ('Schulter', 'Albert', 'Duisburg', 1);
INSERT INTO customers
VALUES (NULL, 'Brunhild', 'Sulcher', 1, 'Süderstade');
INSERT INTO customers
VALUES (NULL, 'Jochen', 'Schmied', 2, 'Solingen');
````
### Select
````sql
SELECT *
FROM dvd_collection;
SELECT title, id
FROM dvd_collection;
SELECT title, director
FROM dvd_collection;
SELECT *
FROM dvd_collection
WHERE director = 'Quentin Tarantino';
SELECT *
FROM dvd_collection
WHERE director = 'Steven Spielberg';
SELECT *
FROM dvd_collection
WHERE director LIKE 'Steven %';
SELECT *
FROM dvd_collection
WHERE duration_minutes > 120;
SELECT *
FROM dvd_collection
WHERE director IN ('Quentin Tarantino', 'Steven Spielberg');
SELECT *
FROM dvd_collection
WHERE director = 'Quentin Tarantino'
  AND duration_minutes < 90;
SELECT *
FROM dvd_collection
WHERE title LIKE '%Sibirien%';
SELECT *
FROM dvd_collection
WHERE title LIKE 'Das grosse Rennen%';
SELECT *
FROM dvd_collection
ORDER BY director;
SELECT *
FROM dvd_collection
ORDER BY director, title;
SELECT *
FROM dvd_collection
WHERE director = 'Quentin Tarantino'
ORDER BY duration_minutes DESC;
````
# Tag 4
## LB1
## Mengenlehre
### Aufgabe 1
Gegeben  
A = {c, e, z, r, d, g, u, x}
B = {c, e, g}
C = {r, d, g, t}
D = {e, z, u}
E = {z, r, u}
Beurteilung der Teilmengen-Beziehungen:  
- **a** B ⊂ A  Richtig (c, e, g ∈ A)  
- **b** C ⊂ A  Falsch (t ∉ A)  
- **c** E ⊂ A  Richtig (z, r, u ∈ A)  
- **d** B ⊂ C  Falsch (c, e ∉ C)  
- **e** E ⊂ C  Falsch (z, u ∉ C)  
### Aufgabe 2
Gegeben  
A = {1, 2, 3, 4, 5}
B = {2, 5}
C = {3, 5, 7, 9}
a **A ∩ B**  
{2, 5}
b **A ∪ C**  
{1, 2, 3, 4, 5, 7, 9}
c **Bc** (Komplement von B in A, also A \ B)  
{1, 3, 4}
d **B \ C**  
{2}
e **C \ B**  
{3, 7, 9}
---
### Aufgabe 3
Eigene Beispiele mit bezeichnenden Mengen:
 **⊂ (Teilmenge)**  
   - Mengen:  
     ```
     Nahrungsmittel = { Obst, Süssigkeiten, Fisch, Getreide }
     Pflanzliches    = { Obst, Getreide }
     ```  
   - Beziehung:  
     ```
     Pflanzliches ⊂ Nahrungsmittel
     ```
 **∩ (Schnittmenge)**  
   - Mengen:  
     ```
     Obst           = { Birne, Weintraube, Erdbeere }
     RotFrüchte   = { Erdebere, Himmbeere, Apfel }
     ```  
   - Schnittmenge:  
     ```
     Obst ∩ GelbeFrüchte = { Erdbeere }
     ```
## Select join
## 1. Datenbank löschen und neu anlegen
```sql
DROP DATABASE IF EXISTS `kunden`;
CREATE DATABASE IF NOT EXISTS `kunden`;
USE `kunden`;
```
## 2. Tabellenstrukturen
### Tabelle `orte`
```sql
DROP TABLE IF EXISTS `orte`;
CREATE TABLE `orte` (
  `id_postleitzahl` VARCHAR(5)  NOT NULL,
  `name`            VARCHAR(255) NOT NULL,
  `einwohnerzahl`   INT(11)      DEFAULT NULL,
  PRIMARY KEY (`id_postleitzahl`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1;
```
### Tabelle `kunden`
```sql
DROP TABLE IF EXISTS `kunden`;
CREATE TABLE `kunden` (
  `kunde_id`            INT(11)      NOT NULL AUTO_INCREMENT,
  `name`                VARCHAR(200) NOT NULL,
  `fk_ort_postleitzahl` VARCHAR(5)   NOT NULL,
  PRIMARY KEY (`kunde_id`),
  KEY (`fk_ort_postleitzahl`)
) ENGINE=InnoDB AUTO_INCREMENT=11 DEFAULT CHARSET=latin1;
```
## 3. Beispieldaten einfügen
### Orte
```sql
INSERT INTO `orte` (`id_postleitzahl`, `name`, `einwohnerzahl`) VALUES
  ('80995','München',      1000000),
  ('79312','Emmendingen',     40000),
  ('79111','Freiburg',       280000),
  ('20095','Hamburg',       2000000);
```
### Kunden
```sql
INSERT INTO `kunden` (`kunde_id`,`name`,`fk_ort_postleitzahl`) VALUES
  (1,'John',      '79111'),
  (2,'Herbert',   '79312'),
  (3,'Sabina',    '79312'),
  (4,'Mary',      '79111'),
  (5,'Heinrich',  '79111'),
  (6,'Usal',      '80995'),
  (7,'Johannes',  '80995'),
  (8,'Carla',     '79312'),
  (9,'Ludowika',  '79111'),
  (10,'Niemand',  '99999');   
```
## 5. Beispielabfragen (a – g)
### a) Name, Postleitzahl und Wohnort aller Kunden
```sql
SELECT
  k.name                   AS kundenname,
  k.fk_ort_postleitzahl    AS postleitzahl,
  o.name                   AS ort
FROM kunden k
JOIN orte  o ON k.fk_ort_postleitzahl = o.id_postleitzahl;
```
### b) Name und Wohnort aller Kunden mit der Postleitzahl 79312
```sql
SELECT
  k.name AS kundenname,
  o.name AS ort
FROM kunden k
JOIN orte  o ON k.fk_ort_postleitzahl = o.id_postleitzahl
WHERE k.fk_ort_postleitzahl = '79312';
```
### c) Name und Wohnort aller Kunden, die in Emmendingen wohnen
```sql
SELECT
  k.name AS kundenname,
  o.name AS ort
FROM kunden k
JOIN orte  o ON k.fk_ort_postleitzahl = o.id_postleitzahl
WHERE o.name = 'Emmendingen';
```
### d) Name, Wohnort und Einwohnerzahl für Kunden in Orten > 70 000 Einwohner
```sql
SELECT
  k.name          AS kundenname,
  o.name          AS ort,
  o.einwohnerzahl AS einwohner
FROM kunden k
JOIN orte  o ON k.fk_ort_postleitzahl = o.id_postleitzahl
WHERE o.einwohnerzahl > 70000;
```
### e) Alle Orte mit weniger als 1 000 000 Einwohnern
```sql
SELECT
  id_postleitzahl,
  name          AS ort,
  einwohnerzahl
FROM orte
WHERE einwohnerzahl < 1000000;
```
### f) Kundenname und Ortname für Orte mit 100 000–1 500 000 Einwohnern
```sql
SELECT
  k.name AS kundenname,
  o.name AS ort
FROM kunden k
JOIN orte  o ON k.fk_ort_postleitzahl = o.id_postleitzahl
WHERE o.einwohnerzahl BETWEEN 100000 AND 1500000;
```
### g) Kundenname, Postleitzahl und Ort – Bedingungen:
- Kundenname enthält „e“
- Ortsname enthält „u“ **ODER** „r**
```sql
SELECT
  k.name                AS kundenname,
  k.fk_ort_postleitzahl AS postleitzahl,
  o.name                AS ort
FROM kunden k
JOIN orte  o ON k.fk_ort_postleitzahl = o.id_postleitzahl
WHERE k.name LIKE '%e%'
  AND (o.name LIKE '%u%' OR o.name LIKE '%r%');
```

## 1) Lieferanten mit Sitz in Freiburg
```sql
SELECT
  l.name        AS lieferant,
  o.name        AS ort,
  o.postleitzahl
FROM lieferanten l
JOIN orte       o ON l.orte_orte_id = o.orte_id
WHERE o.name = 'Freiburg';
```
## 2) Verlage mit Sitz in München
```sql
SELECT
  v.name        AS verlag,
  o.name        AS ort
FROM verlage v
JOIN orte    o ON v.orte_orte_id = o.orte_id
WHERE o.name = 'München';
```
## 3) Bücher aus dem Verlag „Assal“
```sql
SELECT
  b.titel,
  b.erscheinungsjahr,
  v.name        AS verlag
FROM buecher b
JOIN verlage v ON b.verlage_verlage_id = v.verlage_id
WHERE v.name = 'Assal'
ORDER BY b.erscheinungsjahr DESC;
```
## 4) Bücher des Lieferanten „Schustermann“
```sql
SELECT
  b.titel,
  l.name        AS lieferant
FROM buecher b
JOIN buecher_has_lieferanten bl ON b.buecher_id = bl.buecher_buecher_id
JOIN lieferanten l ON bl.lieferanten_lieferanten_id = l.lieferanten_id
WHERE l.name = 'Schustermann';
```
## 5) Alle Bücher der Sparte „Thriller“
```sql
SELECT
  b.titel,
  s.bezeichnung AS sparte
FROM buecher b
JOIN buecher_has_sparten bs ON b.buecher_id = bs.buecher_buecher_id
JOIN sparten s ON bs.sparten_sparten_id = s.sparten_id
WHERE s.bezeichnung = 'Thriller'
ORDER BY b.titel;
```
## 6) Alle Liebesromane („Liebe“)
```sql
SELECT
  b.titel,
  s.bezeichnung AS sparte,
  v.name        AS verlag
FROM buecher b
JOIN buecher_has_sparten bs ON b.buecher_id = bs.buecher_buecher_id
JOIN sparten s ON bs.sparten_sparten_id = s.sparten_id
JOIN verlage v ON b.verlage_verlage_id = v.verlage_id
WHERE s.bezeichnung = 'Liebe'
ORDER BY b.titel;
```
## 7) Bücher von Sabrina Müller
```sql
SELECT
  a.nachname,
  a.vorname,
  b.titel
FROM autoren a
JOIN autoren_has_buecher ab ON a.autoren_id = ab.autoren_autoren_id
JOIN buecher b ON ab.buecher_buecher_id = b.buecher_id
WHERE a.vorname = 'Sabrina'
  AND a.nachname = 'Müller'
ORDER BY b.titel DESC;
```
## 8) Thriller von Sabrina Müller
```sql
SELECT
  CONCAT(a.vorname, ' ', a.nachname) AS autor,
  b.titel,
  s.bezeichnung                     AS sparte
FROM autoren a
JOIN autoren_has_buecher ab ON a.autoren_id = ab.autoren_autoren_id
JOIN buecher b ON ab.buecher_buecher_id = b.buecher_id
JOIN buecher_has_sparten bs ON b.buecher_id = bs.buecher_buecher_id
JOIN sparten s ON bs.sparten_sparten_id = s.sparten_id
WHERE a.vorname = 'Sabrina'
  AND a.nachname = 'Müller'
  AND s.bezeichnung = 'Thriller';
```
## 9) Thriller ODER Humor von Sabrina Müller
```sql
SELECT
  CONCAT(a.vorname, ' ', a.nachname) AS autor,
  b.titel,
  GROUP_CONCAT(DISTINCT s.bezeichnung ORDER BY s.bezeichnung SEPARATOR ', ') AS sparten
FROM autoren a
JOIN autoren_has_buecher ab ON a.autoren_id = ab.autoren_autoren_id
JOIN buecher b ON ab.buecher_buecher_id = b.buecher_id
JOIN buecher_has_sparten bs ON b.buecher_id = bs.buecher_buecher_id
JOIN sparten s ON bs.sparten_sparten_id = s.sparten_id
WHERE a.vorname = 'Sabrina'
  AND a.nachname = 'Müller'
  AND s.bezeichnung IN ('Thriller', 'Humor')
GROUP BY b.titel
ORDER BY b.titel;
```
# Tag 5
## Warum lassen sich Datensätze nicht beliebig entfernen?
In relationalen Datenbanken bestehen zwischen Tabellen oft Abhängigkeiten. Wird ein Eintrag gelöscht, auf den andere Tabellen noch verweisen, bleiben sogenannte verwaiste Fremdschlüssel zurück. Dadurch wird die Datenkonsistenz verletzt – Abfragen liefern dann unter Umständen fehlerhafte Ergebnisse.
## Wer verhindert das?
Das Datenbankmanagementsystem (DBMS) sorgt für die referenzielle Integrität. Ist ein Fremdschlüssel definiert, prüft die Datenbank bei jedem INSERT, UPDATE oder DELETE, ob der Verweis gültig bleibt. Falls nicht, wird der Vorgang abgebrochen, typischerweise mit Fehlercode 1451 oder 1452.
## „4000 Basel“ durch „3000 Bern“ ersetzen
```sql 
DELETE FROM tbl_orte
UPDATE tbl_orte
SET    PLZ = '3000',
       Ortsbezeichnung = 'Bern'
WHERE  ID_Ort = 5;
```
## Warum nicht einfach ON DELETE CASCADE?
Die Option CASCADE würde bei Löschung von „Basel“ alle verknüpften Datensätze automatisch mitlöschen – etwa Stationen oder historische Routen. Das ist meist nicht gewünscht, da wichtige Daten verloren gehen könnten. Daher wird bei kritischen Beziehungen oft gezielt RESTRICT oder NO ACTION verwendet, um Löschvorgänge zu kontrollieren.
## Schema CASCADE
````sql
DROP SCHEMA IF EXISTS fk_tests;
CREATE SCHEMA fk_tests DEFAULT CHARACTER SET utf8;
USE fk_tests;
CREATE TABLE locations (
  postal_code VARCHAR(5) PRIMARY KEY,
  city_name   VARCHAR(45)
) ENGINE=InnoDB;
INSERT INTO locations (postal_code, city_name) VALUES
  ('10000','Musterhausen'),
  ('79092','Freiburg'),
  ('79102','Freiburg'),
  ('79312','Emmendingen');
CREATE TABLE customers (
  customer_id      INT AUTO_INCREMENT PRIMARY KEY,
  customer_name    VARCHAR(45),
  postal_code_ref  VARCHAR(5),
  CONSTRAINT fk_customers_locations
    FOREIGN KEY (postal_code_ref)
    REFERENCES locations (postal_code)
    ON DELETE CASCADE
    ON UPDATE CASCADE
);
INSERT INTO customers (customer_name, postal_code_ref) VALUES
  ('Huber','10000'),
  ('Schmitt','10000'),
  ('Müller','79312'),
  ('Maier','79312'),
  ('Metz','79092'),
  ('Schmied','79102');
DELETE FROM locations;
SELECT * FROM customers; 
DROP TABLE IF EXISTS customers;
DROP TABLE IF EXISTS locations;
CREATE TABLE customers (
  customer_id      INT AUTO_INCREMENT PRIMARY KEY,
  customer_name    VARCHAR(45),
  postal_code_ref  VARCHAR(5),
  CONSTRAINT fk_customers_locations
    FOREIGN KEY (postal_code_ref)
    REFERENCES locations (postal_code)
    ON DELETE RESTRICT
    ON UPDATE RESTRICT
);
DELETE FROM locations
WHERE city_name = 'Emmendingen';
UPDATE locations
SET postal_code = '99999'
WHERE postal_code = '10000';
DROP TABLE IF EXISTS customers;
DROP TABLE IF EXISTS locations;
CREATE TABLE customers (
  customer_id      INT AUTO_INCREMENT PRIMARY KEY,
  customer_name    VARCHAR(45),
  postal_code_ref  VARCHAR(5),
  CONSTRAINT fk_customers_locations
    FOREIGN KEY (postal_code_ref)
    REFERENCES locations (postal_code)
    ON DELETE SET NULL
    ON UPDATE NO ACTION
);
DELETE FROM locations
WHERE city_name = 'Emmendingen';
SELECT customer_id, customer_name, postal_code_ref
FROM customers
WHERE postal_code_ref IS NULL;
UPDATE locations
SET postal_code = '99999'
WHERE postal_code = '10000';
````
# Tag 6
## SubQueries
```sql
SELECT * 
FROM buecher b 
WHERE b.verkaufspreis = (SELECT MAX(verkaufspreis) FROM buecher);
SELECT * 
FROM buecher b 
WHERE b.verkaufspreis = (SELECT MIN(verkaufspreis) FROM buecher);
SELECT * 
FROM buecher b 
WHERE b.einkaufspreis > (SELECT AVG(einkaufspreis) FROM buecher);
SELECT DISTINCT b.* 
FROM buecher b 
WHERE b.einkaufspreis > (
    SELECT AVG(b_in.einkaufspreis) 
    FROM buecher b_in 
    JOIN buecher_has_sparten bs_in ON b_in.buecher_id = bs_in.buecher_buecher_id 
    JOIN sparten s_in ON bs_in.sparten_sparten_id = s_in.sparten_id 
    WHERE s_in.bezeichnung = 'Thriller'
);
SELECT b.* 
FROM buecher b 
JOIN buecher_has_sparten bs ON b.buecher_id = bs.buecher_buecher_id 
JOIN sparten s ON bs.sparten_sparten_id = s.sparten_id 
WHERE s.bezeichnung = 'Thriller' 
AND b.einkaufspreis > (
    SELECT AVG(b_in.einkaufspreis) 
    FROM buecher b_in 
    JOIN buecher_has_sparten bs_in ON b_in.buecher_id = bs_in.buecher_buecher_id 
    JOIN sparten s_in ON bs_in.sparten_sparten_id = s_in.sparten_id 
    WHERE s_in.bezeichnung = 'Thriller'
);
SELECT b.*, (b.verkaufspreis - b.einkaufspreis) AS gewinn 
FROM buecher b 
WHERE (b.verkaufspreis - b.einkaufspreis) > (
    SELECT AVG(verkaufspreis - einkaufspreis) 
    FROM buecher 
    WHERE buecher_id <> 22
);
```
```sql
SELECT SUM(avg_einkaufspreis) AS summe_avg_einkaufspreise
FROM (
    SELECT   s.sparten_id,
             s.bezeichnung,
             AVG(b.einkaufspreis) AS avg_einkaufspreis
    FROM     sparten              s
    JOIN     buecher_has_sparten  bs ON s.sparten_id = bs.sparten_sparten_id
    JOIN     buecher              b  ON bs.buecher_buecher_id = b.buecher_id
    GROUP BY s.sparten_id, s.bezeichnung
    HAVING   s.bezeichnung <> 'Humor'         
         AND AVG(b.einkaufspreis) > 10         
) AS sparten_preise;
SELECT   vorname,
         nachname,
         anzahl_buecher
FROM (
    SELECT  a.autoren_id,
            a.vorname,
            a.nachname,
            COUNT(ab.buecher_buecher_id) AS anzahl_buecher
    FROM    autoren              a
    JOIN    autoren_has_buecher  ab ON a.autoren_id = ab.autoren_autoren_id
    GROUP BY a.autoren_id, a.vorname, a.nachname
    HAVING   COUNT(*) > 4
) AS bekannte_autoren;
SELECT COUNT(*) AS anzahl_bekannter_autoren
FROM (
    SELECT  a.autoren_id
    FROM    autoren              a
    JOIN    autoren_has_buecher  ab ON a.autoren_id = ab.autoren_autoren_id
    GROUP BY a.autoren_id
    HAVING  COUNT(*) > 4
) AS bekannte_autoren;
SELECT AVG(avg_gewinn) AS gesamt_ø_gewinn_der_verlage
FROM (
    SELECT  v.verlage_id,
            v.name,
            AVG(b.verkaufspreis - b.einkaufspreis) AS avg_gewinn
    FROM    verlage v
    JOIN    buecher  b ON v.verlage_id = b.verlage_verlage_id
    GROUP BY v.verlage_id, v.name
    HAVING  avg_gewinn < 10                  
) AS schwachverdiener;
```
# Tag 7
## Backup Konzepte
Datenbanksysteme sind essenziell für die Funktionalität von Websites und Unternehmenssoftware, da sie wichtige Daten wie Personal- und Finanzinformationen speichern. Ein Ausfall oder Verlust dieser Daten kann zu erheblichen Problemen führen. Oft entsteht ein Datenverlust durch technische Fehler oder Benutzerfehler, und nicht durch äußere Angriffe. Eine regelmäßige Datensicherung ist daher notwendig, um die Daten im Falle eines Verlustes wiederherzustellen.
### Möglichkeiten zur Sicherung von Datenbanken
Es gibt zwei Hauptarten der Datensicherung: Online- und Offline-Backups. Beim Online-Backup wird die Datenbank während des Sicherungsprozesses nicht heruntergefahren, während beim Offline-Backup die Datenbank während der Sicherung nicht verfügbar ist.
Es gibt verschiedene Methoden zur Durchführung von Backups:
- **Voll-Backup**: Sichert alle Daten, benötigt jedoch viel Speicherplatz.
- **Differentielles Backup**: Sichert nur Änderungen seit dem letzten Voll-Backup und spart Speicherplatz.
- **Inkrementelles Backup**: Sichert nur die Änderungen seit der letzten Sicherung und benötigt am wenigsten Speicherplatz.
### Tools zur Erstellung von Backups
- **MySQLDump**: Ein schneller Befehl für Voll-Backups über die Shell.
- **phpMyAdmin**: Ermöglicht das Exportieren von SQL-Datenbanken, hat aber bei großen Datenbanken Einschränkungen.
- **BigDump**: Ergänzt phpMyAdmin und kann große Backups einspielen.
- **HeidiSQL**: Eine Windows-basierte Lösung, die keine Probleme mit großen Backups hat, jedoch keine Automatisierung bietet.
- **Mariabackup**: Ein Open-Source-Tool für physische Online-Backups, entwickelt von MariaDB.
### Sicherheit und Schutz der Datenbanken
Datenbanken enthalten oft sensible Informationen und sind daher besonders schützenswert. Regelmäßige Backups verhindern Datenverlust durch Hardwarefehler oder Benutzerfehler. Um die Daten langfristig sicher zu speichern, sollten Backups regelmäßig durchgeführt und auf sicheren, externen Speichermedien abgelegt werden.
# Tag 8
In dieser Praxisarbeit habe ich CSV-Daten in eine Datenbank importiert und sie auf die dritte Normalform (3. NF) gebracht. Dabei wurden die Daten strukturiert in Tabellen übertragen und redundantem Speicherbedarf eliminiert.
Die wichtigsten Schritte beinhalteten den Import der CSV-Daten, die Normalisierung der Tabellen sowie die Durchführung von Tests zur Überprüfung der Datenintegrität.
Ergebniss = Tag 9
# Tag 9
Als erstes hatten wir die LB2.
Danach weiter an der Projektarbeit gearbeitet.
## Projektarbeit
## 1 Excel → Erste Normalform (1. NF) & CSV-Exporte
| Ursprüngliche Spalte | Atomare Aufteilung (1. NF)             | Beispiel-CSV (`;`-Separator) |
|---------------------|----------------------------------------|-----------------------------|
| Schüler             | `schueler_id`; `vorname`; `nachname`  | **Schueler.csv**<br>1;Inge;Sommer |
| Geb.-Datum          | `geburtsdatum`                         | (siehe oben) |
| Klasse              | `klasse_id`; `klassenbezeichnung`      | **Klasse.csv**<br>1;2a |
| Freifach            | `freifach_id`; `bezeichnung`           | **Freifach.csv**<br>1;Chor |
| Lehrer              | `lehrer_id`; `vorname`; `nachname`     | **Lehrer.csv**<br>1;Anna;Meier |
| Kombinationen       | `teilnahme_id`; <FKs Schüler/Klasse/Freifach/Lehrer> | **Teilnahme.csv**<br>1;1;1;1;1 |

## 2 Logisches ERD (mind. 2. NF)
```
Schueler   1——∞  Teilnahme  ∞——1  Freifach
               ∞         ∞
                \       /
                 1——∞  Klasse
                   |
                   ∞
                  Lehrer
```
| Tabelle    | Primärschlüssel | Wichtige Attribute | Kardinalitäten | Anmerkungen |
|------------|-----------------|--------------------|----------------|-------------|
| Schueler   | schueler_id PK  | vorname, nachname, geburtsdatum | 1 Schueler hat 0…* Teilnahmen | – |
| Klasse     | klasse_id PK    | klassenbezeichnung              | 1 Klasse hat 0…* Schüler / 0…* Teilnahmen | – |
| Freifach   | freifach_id PK  | bezeichnung                     | 1 Freifach hat 0…* Teilnahmen | – |
| Lehrer     | lehrer_id PK    | vorname, nachname               | 1 Lehrer leitet 0…* Teilnahmen | – |
| Teilnahme  | teilnahme_id PK | FK schueler_id, klasse_id,<br>FK freifach_id, lehrer_id | – | Brückentabelle |
## 3 Physisches ERD & SQL-DDL (Forward Engineering)
```sql
CREATE DATABASE IF NOT EXISTS Freifaecher DEFAULT CHARACTER SET utf8mb4;
USE Freifaecher;
CREATE TABLE Klasse (
  klasse_id          INT AUTO_INCREMENT PRIMARY KEY,
  klassenbez         VARCHAR(10) NOT NULL UNIQUE
) ENGINE=InnoDB;

CREATE TABLE Freifach (
  freifach_id        INT AUTO_INCREMENT PRIMARY KEY,
  bezeichnung        VARCHAR(50) NOT NULL UNIQUE
) ENGINE=InnoDB;

CREATE TABLE Lehrer (
  lehrer_id          INT AUTO_INCREMENT PRIMARY KEY,
  vorname            VARCHAR(40) NOT NULL,
  nachname           VARCHAR(40) NOT NULL,
  CONSTRAINT uq_lehrer_name UNIQUE (vorname, nachname)
) ENGINE=InnoDB;

CREATE TABLE Schueler (
  schueler_id        INT AUTO_INCREMENT PRIMARY KEY,
  vorname            VARCHAR(40) NOT NULL,
  nachname           VARCHAR(40) NOT NULL,
  geburtsdatum       DATE        NOT NULL,
  klasse_id          INT NOT NULL,
  CONSTRAINT fk_schueler_klasse FOREIGN KEY (klasse_id)
            REFERENCES Klasse (klasse_id)
            ON UPDATE CASCADE ON DELETE RESTRICT
) ENGINE=InnoDB;

CREATE TABLE Teilnahme (
  teilnahme_id       INT AUTO_INCREMENT PRIMARY KEY,
  schueler_id        INT NOT NULL,
  freifach_id        INT NOT NULL,
  lehrer_id          INT NOT NULL,
  UNIQUE (schueler_id, freifach_id),   -- 1 Schüler <= 1 Teilnahme je Freifach
  CONSTRAINT fk_teiln_schueler FOREIGN KEY (schueler_id) REFERENCES Schueler(schueler_id),
  CONSTRAINT fk_teiln_freifach FOREIGN KEY (freifach_id) REFERENCES Freifach(freifach_id),
  CONSTRAINT fk_teiln_lehrer   FOREIGN KEY (lehrer_id)   REFERENCES Lehrer(lehrer_id)
) ENGINE=InnoDB;
```
## 4 CSV-Import mit `LOAD DATA`
```sql
LOAD DATA LOCAL INFILE '/path/to/Klasse.csv'
INTO TABLE Klasse
FIELDS TERMINATED BY ';'
LINES TERMINATED BY '\n'
(klasse_id, klassenbez);

LOAD DATA LOCAL INFILE '/path/to/Freifach.csv'
INTO TABLE Freifach
FIELDS TERMINATED BY ';'
LINES TERMINATED BY '\n'
(freifach_id, bezeichnung);
```
> Kontroll­abfrage nach jedem Import (Beispiel):
> ```sql
> SELECT COUNT(*) FROM Schueler;
> SELECT COUNT(*) FROM Teilnahme WHERE schueler_id NOT IN (SELECT schueler_id FROM Schueler);
> ```
## 5 Datenbereinigung
Beispiel für Cleanup-Skripte (leere Nachnamen, Dubletten …):
```sql
UPDATE Schueler SET nachname = NULL WHERE TRIM(nachname) = '';
DELETE l2 FROM Lehrer l1
JOIN Lehrer l2 ON l1.lehrer_id < l2.lehrer_id
              AND l1.vorname = l2.vorname AND l1.nachname = l2.nachname;
```
## 6 Tests – Soll/Ist Vergleich
```sql
SELECT klassenbez, COUNT(*) AS anzahl
FROM   Schueler s JOIN Klasse k USING (klasse_id)
GROUP  BY k.klasse_id
ORDER  BY klassenbez;
```
## 7 +290 Testdatensätze generieren
```sql
-- Beispiel mit Faker (falls du Python + Faker verwenden möchtest)
-- python - <<EOF
-- from faker import Faker, providers; import csv, random, datetime
-- fake = Faker('de_DE');
-- with open('Schueler_extra.csv','w',newline='') as f:
--     w = csv.writer(f, delimiter=';')
--     for i in range(290):
--         dt = fake.date_between_dates(date_start=datetime.date(2005,1,1), date_end=datetime.date(2008,12,31))
--         w.writerow(['', fake.first_name(), fake.last_name(), dt, random.randint(1,6)])
-- EOF
```
## 8 Abfrage-Aufgaben
```sql
SELECT COUNT(*) AS teilnehmer_ingesommer
FROM   Teilnahme t
JOIN   Schueler  s  ON t.schueler_id = s.schueler_id
JOIN   Lehrer    l  ON t.lehrer_id   = l.lehrer_id
WHERE  l.vorname = 'Inge' AND l.nachname = 'Sommer';
SELECT k.klassenbez, COUNT(*) AS anzahl_teilnehmer
FROM   Teilnahme t
JOIN   Schueler s  ON t.schueler_id = s.schueler_id
JOIN   Klasse  k  ON s.klasse_id   = k.klasse_id
GROUP  BY k.klasse_id
ORDER  BY k.klassenbez;
SELECT s.vorname, s.nachname, f.bezeichnung
FROM   Teilnahme t
JOIN   Schueler s ON t.schueler_id = s.schueler_id
JOIN   Freifach f ON t.freifach_id = f.freifach_id
WHERE  f.bezeichnung IN ('Chor','Elektronik');
```
### Ergebnisse in Datei speichern (`SELECT … INTO OUTFILE`)
```sql
SELECT k.klassenbez, COUNT(*) AS anzahl_teilnehmer
INTO OUTFILE '/tmp/klassen_teilnehmer.csv'
FIELDS TERMINATED BY ';' LINES TERMINATED BY '\n'
FROM   Teilnahme t
JOIN   Schueler s ON t.schueler_id = s.schueler_id
JOIN   Klasse  k ON s.klasse_id   = k.klasse_id
GROUP  BY k.klasse_id;
```
## 9 Backup der DB `Freifaecher`
```bash
mysqldump -u backup_user -p --databases Freifaecher           --routines --events --triggers           --single-transaction --quick --add-drop-table           > Freifaecher_backup_$(date +%F).sql
```

# Tag 10 
Ich habe mein Lernjournal erfolgreich fertiggestellt und mich intensiv mit dem Thema "Common Table Expressions" (CTEs) und "Stored Procedures" auseinandergesetzt. Dabei habe ich sowohl die Grundlagen als auch die praktischen Anwendungen dieser Konzepte erlernt. Besonders spannend fand ich, wie CTEs die Lesbarkeit und Wartbarkeit von SQL-Abfragen verbessern können, während Stored Procedures die Wiederverwendbarkeit und Modularität von Code ermöglichen.
## Hintergrund und Vorteile von Stored Procedures
Stored Procedures (gespeicherte Prozeduren) sind vordefinierte, wiederverwendbare SQL-Programme, die in einer Datenbank gespeichert und nach Bedarf ausgeführt werden können.
Wiederverwendbarkeit: Einmal definiert, können sie jederzeit genutzt werden.
Zentralisierung der Logik: Komplexe Geschäftsprozesse werden serverseitig verwaltet, was die Nutzung von Client-Skripten vermeidet.
Leistung: Die direkte Ausführung auf dem Datenbankserver verringert die Notwendigkeit für Netzwerkaufrufe und verbessert die Performance.
Sicherheit: Nutzer benötigen nur die Berechtigung zur Ausführung der Prozeduren (EXECUTE-Rechte), nicht jedoch zu Änderungen an den zugrunde liegenden Tabellen (DML-Rechte).
## Prozeduren
````sql
DELIMITER $$
CREATE PROCEDURE GetTeilnehmerProLehrer (IN LehrerID INT)
BEGIN
    SELECT l.lehrer_id, 
           l.vorname, 
           l.nachname, 
           COUNT(t.teilnahme_id) AS teilnehmerzahl
    FROM   Lehrer l
    LEFT JOIN Teilnahme t ON l.lehrer_id = t.lehrer_id
    WHERE  l.lehrer_id = LehrerID
    GROUP BY l.lehrer_id;
END $$
CREATE PROCEDURE KlassenÜbersicht ()
BEGIN
    SELECT k.klassenbezeichnung, 
           COUNT(DISTINCT s.schueler_id) AS anzahl_schueler, 
           COUNT(t.teilnahme_id)         AS anzahl_teilnahmen, 
           MAX(t.teilnahme_id)           AS max_teilnahme
    FROM   Klasse k
    LEFT JOIN Schueler s ON k.klasse_id = s.klasse_id
    LEFT JOIN Teilnahme t ON s.schueler_id = t.schueler_id
    GROUP BY k.klasse_id
    ORDER BY k.klassenbezeichnung;
END $$
CREATE PROCEDURE FreifachStatistik ()
BEGIN
    SELECT f.name, 
           COUNT(t.teilnahme_id) AS teilnehmer, 
           MAX(t.teilnahme_id)   AS max_teilnahme, 
           AVG(sub.cnt)          AS durchschnitt_pro_lehrer
    FROM   Freifach f
    LEFT JOIN Teilnahme t ON f.freifach_id = t.freifach_id
    LEFT JOIN (
        SELECT lehrer_id, freifach_id, COUNT(*) AS cnt
        FROM   Teilnahme
        GROUP  BY lehrer_id, freifach_id
    ) sub ON sub.freifach_id = f.freifach_id
    GROUP BY f.freifach_id;
END $$
DELIMITER ;
````
## für Aufrufe
````sql
CALL GetTeilnehmerProLehrer(1);
CALL KlassenÜbersicht();
CALL FreifachStatistik();
````
## Berechtigungen
````sql
GRANT EXECUTE ON PROCEDURE Freifaecher.GetTeilnehmerProLehrer TO 'app_user'@'%';
GRANT EXECUTE ON PROCEDURE Freifaecher.KlassenÜbersicht TO 'app_user'@'%';
GRANT EXECUTE ON PROCEDURE Freifaecher.FreifachStatistik TO 'app_user'@'%';
````