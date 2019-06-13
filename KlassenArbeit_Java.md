## Japanische Schriftzeichen

## Schritt **1**: Vorbereitung

Lege ein Array mit den Japanischen Schriftzeichen an.

## Schritt **2**: Grobes Verständnis

Jetzt müssen die 10er Potenzen abgearbeitet werden. Zuallerst fragen wir den Benutzer nach der Zahl die wir umwandeln sollen dann brauchen wir eine Ergebnis Variable eines geigenten Datentyps :D, sowie eine Variable für das Speichern der aktuellen Potenz. Für das Checken der Potenzen verwenden wir eine Schleife. Sie läuft über alle Potenzen und prüft ob diese vorhanden/gebraucht werden.

## Schritt **3**: Der Algorithmus
Wir haben also eine Ergebnisvariable und die Variable für die aktuelle Potenz. In der Schleife legen wir nun eine neue Zahl an welche die Anzahl, der Potenz angibt. Wenn sie größer 0 ist, wir also eine Potenz gefunden haben fügen wir das zuerst das Schriftzeichen für die Anzahl (also wie) häufig die Potenz vorkommt aus dem Array der chinesischen Zeichen an unser Ergebnis an. Dann die Potenz selber -> Du erinnerst dich vielleicht an die Metapher mit den Seiten in einem Buch.
Wir geben unserer BenutzerZahl den Wert des Divisionsrestes und veringern die Potenz zu nächst kleinern.

Wenn die Schleife fertig ist, prüfen wir ob in der BenutzerZahl noch etwas drinsteht was wir bearbeiten sollten (wenn sie größer 0 ist). Falls ja fügen wir die benutzerZahl einfach als chinesisches Schriftzeichen an das Ergebnis an.

### Beispiel

benutzerZahl: 197_240
* Wir haben also 1 * eine 100_000 Potenz (benutzerZahl / aktuelle Potenz = 1 [Achtung Wert wird gerundet wir brauchen keine Nachkommastellen])

* Es wird überprüft dass die Potenz mehr als einmal vorkommt.

* Falls ja fügen wir das Zeichen für die 1 (die Anzahl) an das Ergenis an. Schließlich fügen wir das Zeichen der Potenz an.

* Schließlich dividieren wir die variable mit der aktuellen Potenz mit 10. Um zur nächst niedrigeren Potenz zu kommen.
* Die benutzerZahl ersetzen wir nun durch den Rest der Division mit der Potenz.

### Beispiel

benutzerZahl: 197_240 : 100_000 = 1,9.. // wir werfen allerdings die Nachkommastellen weg uns geht es ja nur darum wie oft die Potenz vorkam. (100000 kam also 1mal vor)

Nun schreiben wir den Divisionsrest der benutzerzahl und der aktuellen Potenz in die benutzerZahl (Tipp: In Java bekommen wir den Divisionsrest über das % Zeichen)

Die Potenzzahl wird nun durch 10 geteilt und in sich selbst gespeichert. 


* Wenn die Schleife ihre Arbeit getan hat müssen wir noch den SonderFall prüfen dass keine es eine Zahl kleiner 10 war, wir also keine Potenz gefunden haben, oder wir noch einen Rest aus der Schleife übrig haben. 

# Achtung Spoiler:
## Du lernst am meisten wenn du es zuerst selbst probierst -> Google ist dein Freund


## Lösung

### Anmerkungen
Der Code müsste **theoretisch** laufen. Ich habe jetzt leider keine Zeit es auszuprobieren. Die Kommentare auf Deutsch tun mir natürlich auch leid.


```java

import Prog1Tools.IOTools;

public class chineseConversion {


	/*
		Falls irgendetwas mit dem Code nicht stimmen sollte tut es mir leid, ist aber umso besser für dich, dann darst du dich nämlich selbst auf Fehlersuche begeben.
		Ein Kleiner Fehler ist enthalten, (ein logikfehler, vllt findest du ihn ja.
		(tipp: was passiert wenn die Zahlen des Benutzers zu groß werden)
	*/ 

	public static void main(String[] args) {

		String[] chinChars = {"一", "二", "三", "四", "五", "六", "七", "八", "九", "十", "百", "千", "千"};

		int usernum = IOTools.readInteger("Please enter a number: ");
		String output = "";
		
		int power = 10000; // wir starten natürlich mit der größten Potenz

		// wir haben ja 4 Potenzen die wir durchlaufen müssen
		// 10_000, 1_000, 100, 10
		for (int i = 0; i < 4; i++)	{
			int count = (int) userNum / power;

			// wenn wir also eine Potenz gefunden haben die passt
			if (count > 0) { 
				output = output + chinChars[count - 1];
				output = output + chin[chinChars.length -i];
			}
			// Divisionsrest wie oben beschrieben, den müssen wir noch abarbeiten
			userNum = userNum % power; 
			power = power / 10; // nächst kleinere Potenz
		}
		if (userNum > 0) {
			output = output + chinChars[userNum - i];
		}
		System.out.println(output);
	}
}

```
