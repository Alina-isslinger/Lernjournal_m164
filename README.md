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

