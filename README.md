
# Übung 16 - Arrays


## 1. Aufgabe

Setzen Sie folgendes Klassendiagramm um:

<p align="center">
  <img src="/assets/images/UML1.png" alt="Bildbeschreibung" />
</p>

**Beschreibung:**
- Das Array ist immer nur in einem bestimmten Bereich mit gültigen Daten belegt. Bei uns von Index `0` bis `last`. 
- Im Konstruktor wird der Speicherplatz für `n` Elemente im Array `personen` angefordert. Prüfen Sie, ob `n > 1` ist. Wenn nicht, geben Sie eine Fehlermeldung aus und setzen Sie `n = 2`. `last` wird auf `-1` gesetzt.
- `printPersonen()`: Gibt die Elemente des Arrays aus. 
- `einfuegenPosition(Person p, int pos)`: Fügt `p` an der Position `pos` ein. Prüfen Sie, ob `pos` einen gültigen Wert hat und vergrößern Sie den gültigen Bereich.
- `einfuegenAnfang()`: Fügt `p` an der ersten Stelle ein. Prüfen Sie, ob genügend Platz vorhanden ist. 
- `einfuegenEnde()`: Fügt `p` an der letzten gültigen Stelle ein. Prüfen Sie, ob genügend Platz vorhanden ist. 
- `loeschenPosition(int pos)`: Löscht die Person an der Stelle `pos` aus dem Array. Prüfen Sie `pos` auf gültige Werte und achten Sie darauf, dass im Array keine Lücken entstehen. 
- `loeschenPerson(Person p)`: Löscht die Person aus dem Array. 
- `int suchen(String name)`: Sucht nach dem Namen einer Person im Array. Beginnen Sie von vorne zu suchen. Rückgabewert soll der Index der gefundenen Person sein. Wurde die Person nicht gefunden, soll `-1` zurückgegeben werden. 
- `int anzahl(String name)`: Liefert die Anzahl an Personen zurück, die den gleichen Namen haben. 

Um Ihr Programm zu testen, erstellen Sie eine `Main`-Klasse, welche die `main`-Methode beinhaltet:
- `main(String[] args)`: Testen Sie Ihr Programm.

## 2. Aufgabe

Setzen Sie folgendes Klassendiagramm um:

<p align="center">
  <img src="/assets/images/UML1.png" alt="Bildbeschreibung" />
</p>

Hinweis für alle Klassen: Benötigte `getter` und `setter` sind zu implementieren.

Beschreibung der `Laden`-Klasse:

- `double verkaufen(String name)`: Verringert die `anzahl` Eigenschaft des Produkts um `1`. Wenn `anzahl` gleich `0` ist, wird das Produkt entfernt. Die Rückgabe ist der `preis`. 
- `double verkaufen(String name, int anzahl)`: Mehrere gleiche Artikel werden verkauft. Falls zu wenige vorhanden sind, wird nichts verkauft. Sonst: siehe `verkaufen(String name)`. 
- `lieferung(Produkt p)`: Fügt ein neues Produkt zum Sortiment hinzu oder erhöht die Anzahl, wenn das Produkt schon vorhanden ist. Dafür muss jedoch auch das Ablaufdatum gleich sein. Ansonsten wird es neu eingefügt.
- `boolean weg(Produkt p)`: Entfernt das Produkt `p`. 
- `sort()`: Sortiert nach dem Ablaufdatum.
- `int abgelaufen(int jahr, int monat)`: Liefert die Anzahl der abgelaufenen Produkte zurück.

Beschreibung der `Produkt`-Klasse:

- `boolean abgelaufen(int jahr, int monat)`: Je nachdem, ob das Produkt abgelaufen ist wird `true` oder `false` zurückgegeben.
- `verkaufen(int anzahl)`: Eine bestimmte `anzahl` wird verkauft. 
- `boolean gleich(Produkt p)`: Gibt `true` zurück, wenn die Produkte gleich sind. Produkte sind gleich, wenn der Name gleich ist. 
- `String toString()`: Bisher haben wir immer eine `print()`-Methode geschrieben, um eine Konsolenausgabe zu machen. Wenn Sie sich jedoch die `Object`-Klasse in der Java-Doc ansehen, wird Ihnen auffallen, dass es dort eine `toString()`- Methode gibt. Diese Methode kann man überschrieben (`override`, mehr dazu zu einem späteren Zeitpunkt). Der Vorteil einer `toString()`-Methode besteht darin, dass sie automatisch aufgerufen wird, sobald sie `System.out.println()` verwenden. 

Beschreibung der `Produkt`-Klasse:

- `boolean gleich(Ablaufdatum ab)`: Gibt `true` zurück, wenn die Ablaufdaten gleich sind. 
- `boolean aelter(Ablaufdatum ab)`: Gibt `true` zurück, wenn `ab` älter ist. 
- `String toString()`: Gibt einen schönen String mit allen Eigenschaften zurück. Für Details siehe `toString()`-Methode von Produkt. 

Um Ihr Programm zu testen, erstellen Sie eine `Main`-Klasse, welche die `main`-Methode beinhaltet:
- `main(String[] args)`: Testen Sie Ihr Programm.

## 3. Aufgabe

Bei dieser Übung bekommen Sie mehr Freiheit und können sich einige Eigenschaften und Methoden selbst überlegen. Bedenken Sie, dass sie einige Methoden möglicherweise auch in anderen Klassen verwenden könnten. Erstellen Sie die drei Klassen `Weinberg`, `Stock`und `Datum`. Prüfen Sie immer auf sinnvolle Werte. Achtung: Vergessen Sie nicht auf Schaltjahre!

Folgendes ist vorgegeben: 

- Klasse `Datum`: 
	- Eigenschaften:
		- `tag`, `monat`, `jahr`
	- Methoden:
		- Entscheiden Sie selbst. 
- Klasse `Stock`: 
	- Eigenschaften:
		- `String sorte`
		- `Datum setzDatum`
		- `int monatGesetzt`
		- `boolean krank`
		- `double ertrag`: Muss größer `0` sein und kleiner als `5` sein.
	- Methoden:
		- Entscheiden Sie selbst. 
- Klasse `Weinberg`: 
	- Eigenschaften:
		- `String name`
		- `Stock[] a`
		- `double groesseInHa`
		- `int last`: Gibt den besetzten Bereich im Array an.
	- Methoden:
		- `Weinberg(int n)`: Erzeugt das Array mit der Größe `n`, wobei `n` mindestens `5` sein muss. 
		- `print()`: Gibt alles aus. 
		- `boolean setzenEnde(Stock s)`: Setzt einen neuen Stock am Ende dazu. Falls kein Platz vorhanden ist, wird `false` zurückgegeben. 
		- `boolean setzenAnfang(Stock s)`: Setzt einen neuen Stock am Anfang dazu. Falls kein Platz vorhanden ist, wird `false` zurückgegeben. 
		- `Stock entfernen()`: Entfernt einen kranken Stock aus dem Array und liefert ihn zurück. 
		- `int anzahlKrank()`: Liefert die Anzahl der kranken Stöcke. 
		- `int ertrag()`: Liefert den Ertrag pro ha. 
		- `double frei()`: Gibt an, wie viele Plätze frei sind - in Prozent.
		- `sortieren()`: Sortiert nach dem Jahr und Monat, in dem der Stock gesetzt wurde. 
		- `anzahlStoecke()`: Liefert die Anzahl der Weinstöcke.
		- `printGruppiert()`: Gibt den Ertrag gruppiert nach der Sorte aus, d.h. gibt es zB die drei Stöcke (nur Sorte + Ertrag): {"A", 5.6}, {"A", 2.6}, {"B", 1.6} so werden die beiden A´s zusammengezählt und folgendes ausgegeben: 
		Sorte A, 8.2
		Sorte B, 1.6
		
Um Ihr Programm zu testen, erstellen Sie eine `Main`-Klasse, welche die `main`-Methode beinhaltet:
- `main(String[] args)`: Testen Sie Ihr Programm.
