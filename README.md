## Was ist SQL?

SQL (Structured Query Language) ist eine Sprache, um mit Datenbanken zu arbeiten.  
Man kann damit Daten speichern, abfragen, ändern und löschen – unabhängig davon, welches Datenbanksystem verwendet wird.

## Wofür wird SQL genutzt?

- **Struktur festlegen** (z. B. Tabellen erstellen)
- **Daten abfragen** (z. B. mit `SELECT`)
- **Daten bearbeiten** (z. B. `INSERT`, `UPDATE`, `DELETE`)
- **Transaktionen steuern** (z. B. `COMMIT`, `ROLLBACK`)
- **Zugriffsrechte verwalten** (z. B. `GRANT`, `REVOKE`)

## Aufgaben
### Tag 1
# Was ich gemacht habe
Zuerst habe ich eine Einführung in Datenbanken bekommen und dabei wichtige Begriffe wie Tabelle, Datenbank, Primärschlüssel und Fremdschlüssel wiederholt. So konnte ich mein Wissen auffrischen.
Danach habe ich wiederholt, wie man Daten normalisiert. Das heisst, ich habe Daten so umgebaut, dass sie gut strukturiert sind und keine doppelten Informationen enthalten. Ich habe dabei die 1., 2. und 3. Normalform wiederholz und ein Beispiel mit einem Tourenplaner durchgearbeitet.
Um praktisch arbeiten zu können, habe ich verschiedene Programme und Tools installiert, mit denen man mit Datenbanken arbeitet:
- **XAMPP** für MariaDB auf dem eigenen Computer    
- **MySQL Workbench**, ein Programm zum Zeichnen von Datenmodellen und Schreiben von SQL-Befehlen
Ausserdem habe ich ein Entity-Relationship-Modell (ERM) erstellt. Das zeigt, wie die Tabellen in der Datenbank miteinander verbunden sind. Daraus habe ich dann ein Entity-Relationship-Diagramm (ERD) gezeichnet, das hilft, die Struktur besser zu verstehen.
Am Ende haben wir nochmal alles wiederholt, um den Stoff zu festigen.
#### Bsp. einer Aufgabe, welche ich gelöst habe:
- **3. Normalform (3NF)**:
### 1. **Zusammenfassung in Stichworten**
- 3 Phasen: konzeptionell (ERM), logisch (ERD), physisch
- Unterschiedliche Datenmodelle je nach Einsatzzweck
- Normalisierung wichtig für Datenkonsistenz und -struktur
- Unterschiedliche Modellierungen je nach Systemtyp (operativ vs. analytisch)

### 2. **Normalisierungsschritte wiederholen**

Schreiben Sie die Schritte zur Normalisierung (bis zur 3. Normalform) in Ihr Lernportfolio:
1. **1. Normalform (1NF)**:  
   - Nur atomare Werte (keine Mehrfachwerte oder Listen in Zellen)
2. **2. Normalform (2NF)**:  
   - Tabelle ist in 1NF  
   - Alle Nicht-Schlüsselattribute hängen vollständig vom Primärschlüssel ab
3. **3. Normalform (3NF)**:  
   - Tabelle ist in 2NF  
   - Keine transitive Abhängigkeit (Nicht-Schlüsselattribute hängen nur vom Primärschlüssel ab)
### 3. **Aufgabe 'Tourenplaner' bearbeiten**
- ERM (konzeptionelles Modell) **von Hand skizzieren**
- ERD (logisches Modell) **in MySQL Workbench umsetzen**
- **Normalisierungsschritte anwenden**, um saubere Tabellenstrukturen zu erstellen

