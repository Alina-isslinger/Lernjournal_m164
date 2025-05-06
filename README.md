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
# Repetition M162 Datentypen

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

## Mehrfachbeziehungen
Bei Mehrfachbeziehungen haben zwei Tabellen mehrere Beziehungen, die unabhängig voneinander sind und jeweils einen anderen Sachverhalt repräsentieren. Um die verschiedenen Beziehungen eindeutig zu kennzeichnen, müssen sie möglichst aussagekräftig beschriftet werden (Rolle). Die Kardinalitäten können natürlich verschieden sein, da die Beziehungen voneinander unabhängig sind. In den Beispielen unten gibt es drei unabhängige Beziehungen zwischen den Entitätstypen `tbl_Fahrten` und `tbl_Orte`. Eine dieser Beziehungen ist die Auflistung der Orte, die bei einer Tour angefahren werden können. Dies ist eine mc:mc-Beziehung und benötigt daher eine Transformationstabelle.
## Rekursion (strenge Hierarchie)
Bei einer Rekursion handelt es sich um eine Beziehung, bei der ein Entitätstyp mit sich selbst in Beziehung steht. Dies tritt oft in Hierarchien auf, z.B. bei einer Unternehmensstruktur, wo jeder Mitarbeiter genau einen Vorgesetzten hat. Eine reine Hierarchie kann innerhalb der gleichen Tabelle abgebildet werden. Sie erhält einen Fremdschlüssel, der auf den Identifikationsschlüssel der eigenen Tabelle verweist.
## Einfache Hierarchie (mit Zwischentabelle)
Wenn mehrere Oberelemente zugelassen sind (z. B. mehrere Projektleiter), handelt es sich um eine mc:mc-Beziehung, die eine Transformationstabelle benötigt. Die beiden Fremdschlüssel der Transformationstabelle zeigen jeweils auf einen Identifikationsschlüssel der gleichen Tabelle, jedoch in unterschiedlichen Rollen.
## Stücklistenproblem
Eine klassische Anwendung der Rekursion in der Datenmodellierung ist die Stücklistenproblematik. Bei modularen Produkten, die sich aus mehreren Einzelteilen zusammensetzen, wird eine Tabelle benötigt, die angibt, welche Teile in welchem Produkt enthalten sind. Diese Beziehung muss rekursiv dargestellt werden, um die Bauteile auf die elementare Ebene herunterzubrechen.
## SQL Code für Mehrfachbeziehungen und Rekursion
```sql
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
# Tag 9

# Tag 10 
Ich habe mein Lernjournal erfolgreich fertiggestellt und mich intensiv mit dem Thema "Common Table Expressions" (CTEs) und "Stored Procedures" auseinandergesetzt. Dabei habe ich sowohl die Grundlagen als auch die praktischen Anwendungen dieser Konzepte erlernt. Besonders spannend fand ich, wie CTEs die Lesbarkeit und Wartbarkeit von SQL-Abfragen verbessern können, während Stored Procedures die Wiederverwendbarkeit und Modularität von Code ermöglichen.