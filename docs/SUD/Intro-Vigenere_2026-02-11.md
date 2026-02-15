---
lastSync: Thu Feb 12 2026 15:14:59 GMT+0100 (Central European Standard Time)
---
2026-02-11 09:45

Tags: [[../../../02 - Tags/$<REDACTED>|$<REDACTED>]] [[../../../02 - Tags/$<REDACTED>_SUD|$<REDACTED>_SUD]] #Kryptologie #Kryptanalyse #Vigenere
 
# 2026-02-11 SUD<REDACTED>

## Unterricht
Lehrer:<REDACTED>

### Themen
- Organisatorisches
	- Nutzen Onenote
	- "Privater Bereich" genutzt zur Notenfindung der sonstigen Mitarbeit
		- Import Markdown!
- Ausschnitt Bildungsplan
	- Schutzbedarfanalyse im eigenen Arbeitsbereich
		- BSI Vorgaben / Empfehlungen
		- Informationssicherheit
		- Anwendung gegen Ende der Unterrichtsreihe
		- IT-Sicherheitsleitlinie
		- Vertraulichkeit
		- Integrität
		- Verfügbarkeit	
	- Krypto
	- DSGVO
> [!NOTE]- Besagter Ausschnitt
> ![[05 - Resources/2026-02-11_Bildungsplan.png]]Contents

### Beispeil: Skytale
- Vermischung der Buchstaben anhand einer Wicklung um einen definierten Durchmesser
- Bei der Annahme eines gleichmäßigen Durchmessers des imaginierten Stabs können wir versuchen alle X Buchstaben aneinander zu reihen. Da der text mehrmals um den Stab "gewickelt" werden muss, muss es weniger Möglichkeiten als die Anzahl der Buchstaben / 2 geben.

### Beispiel: Caesar Verschlüsselung
- "Verschiebung" des Alphabetes um X Positionen
	- -> Es kann nur 26 mögliche Schlüssel geben, Trivial lösbar
- Statistisch anhand der Buchstabenfrequenz lösbar; vorteilhaft, wenn die Ausgangssprache bekannt ist
	- Statistische Gesamtanalyse bei verschiedenen Anordnungen der Buchstabensets empfehlenswert

### Beispiel: Vigenère-Chiffre
>[!INFO]- Aufgaben und PDF
> ![[05 - Resources/1. Kryptographie VigenereSquare-Verfahren_Verschlüsseln.pdf|1. Kryptographie VigenereSquare-Verfahren_Verschlüsseln]]

a)
Als erstes wird ein Vigenère Quadrat Angelegt, bestehend aus 26x26 Zellen, welche das Alphabet A-Z in jeder Zeile Abbilden. Die erste Zeile beginnt mit "A", jede folgende Zeile ist um eins nach links verschoben (in diesem Beispiel, andere Anordnungen sind Denkbar)

Zur Verschlüsselung wird ein Schlüsselwort unter/über den Klartext in wiederholender Art geschrieben, so dass jeder Buchstabe des Klartextes einem Buchstaben des wiederholenden Schlüssel zugeordnet ist.

Für jedes paar wird in der ersten Zeile des Quadrats die Schlüsselkomponente gesucht. In der ersten Spalte wird die Klartextkomponente gesucht. Die Zelle, an dem sich die Zeile und Spalte kreuzen gibt den Buchstaben des Kryptotextes an.

Bei der Entschlüsselung wird das ganze in umgekehrter Reihenfolge angewendet

b)
"HALLOWIEGEHTS" mit dem Schlüssel "ESEL" Verschlüsseln
```
HALLOWIEGEHTS  - Klartext  (Y-Achse)
ESELESELESELE  - Schlüssel (X-Achse)
LSPWSOMPKWLEW  - Kryptotext

```

c)
```
LMSXEGXTXUS  - Kryptotext
ZEBRAZEBRAZ  - Schlüssel
MIRGEHTSGUT  - Klartext
```

d)
```
THISSHIRTISAMUNITION  - Klartext
EXPORTCIRCUMVENTIONE  - Schlüssel
XEXGJAKZKKMMHYABBWBR  - Kryptotext
```

#### Schwächen / Kasiski-Test
[Video zum Kasiski-Verfahren](<REDACTED>)

Der Vigenère-Chiffre ist, insbesondere bei im Verhältnis kurzen Schlüsseln,  anfällig für den Kasiski-Test. Bei diesem wird
- Die wahrscheinliche Länge des Schlüssels bestimmt
	- (Bi)-/Trigramme und längere wiederholende Zeichenfolgen werden gesucht
	- Positionen der Zeichenfolgen werden numerisch aufgeschrieben
	- Differenz der Positionszahlen jeder Zeichenfolge Gruppe wird Ermitteln
	- Zerlegung der Differenzen in ihre Primfaktoren
	- Der größte gemeinsame Teiler gibt wahrscheinlich die Läge des Schlüssels an
	- (Der Kasiski-Test kann auch vielfache der Schlüssellänge erzeugen)
	- Zur weiteren Analyse kann der Friedman-Test angewendet werden
		- Besonders Hilfreich bei Polyalphabetischen Substitutionen
- Der Kryptotext wird in ein Feld mit Zeilenlänge X geschrieben, wobei X gleich der vermuteten Länge des Schlüssels ist.
- Eine Häufigkeitsanalyse der Spalten
- Kontrolle aller wahrscheinlichen Lösungen am Kryptotext
	- Kurze, sehr wahrscheinlich vorkommende Worte als Anhaltspunkte nutzen
- Um Rohrbachs Forderung gerecht zu werden kann aus dem sich ergebenen Klartext mit Hilfe des Kryptotextes der Schlüssel bestimmt werden.

#### Aufgabe:
Anwendung des Kasiski-Verfahrens am [Beispieltext](<REDACTED>)

[Hilfstabelle](<REDACTED>)



## Referenzen
