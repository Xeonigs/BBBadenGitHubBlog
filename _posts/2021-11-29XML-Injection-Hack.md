---
layout: post
title: XML-Injection Hack
---

Informationen und Daten werden meist in Datenbanken oder in bestimmten Files abgespeichert. Gibt es Möglichkeiten diese Files in einer ungewollten Art und Weise zu verändern?

# Aufgabenstellung und Ziele

- Zeigen ob man XML-Dateien manipulieren kann
- Erkären, wieso dass man XML-Dateien manipulieren kann
- Lösungen für solche Problemen vorstellen.

# XML-Dateien

XML-Dateien sind gut um hierarchisch strukturierte Daten abzuspeichern. Hier ein Beispiel einer XML-Datei, welches sich über die ganze Erkärung hinweg zieht:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<users>
	<user id="1">
		<username>administrator</username>
		<password>8dminSec</password>
		<isadmin>1</isadmin>
	</user>
		<user id="2">
		<username>user</username>
		<password>uS3rP8ss</password>
		<isadmin>1</isadmin>
	</user>
</users>
```

# Sicherheitslücke einer XML-Datei

Wir gehen jetzt davon aus, dass man beim Regristrieren eines Users Name und Passwort festlegen kann, aber seinen Adminstatus nicht. Irgendwie kommt man an die Information, wie dieses XML-File aufgebaut ist und überlegt sich dann einen teuflischen Plan.

Man setzt sich ein Username oder Passwort genau so, dass sich dabei direkt zwei neue Users stellen lassen. Dabei wird in unserem Beispiel das Passwort wiefolgt lauten: 

*je m'apelle Velogstell</password><isadmin>1</isadmin></user><user id="69"><username>witzbold</username><password>123*

```xml
<?xml version="1.0" encoding="UTF-8"?>
<users>
	<user id="1">
		<username>administrator</username>
		<password>8dminSec</password>
		<isadmin>1</isadmin>
	</user>
		<user id="2">
		<username>user</username>
		<password>uS3rP8ss</password>
		<isadmin>1</isadmin>
	</user>
	<user id="3">
		<username>eichenberger</username>
		<password>
            
            	  je m'apelle Velogstell</password>
		<isadmin>1</isadmin>
	</user>
	<user id="69">
		<username>witzbold
        
        				  </username>
		<password>123</password>
		<isadmin>0</isadmin>
	</user>
</users>
```

Hier sieht man deutlich, wieso das funktioniert. Man setzt ein gezieltes Passwort, welches dann die Struktur einer XML-Datei ausnutzt um einen Admin zu erstellen und kann alles anstellen, was ein Admin auch kann

# Lösungen

Da gibt es mehrere Lösungsansätze, da diese Sicherheitlücke relativ stumpf ist.

- Passwort und Username Zeichenanzahl beschränken
- Keine Sonderzeichen zulassen
- Sonderzeichen escapen

# Reflexion und Verifizierung

**Habe ich bewiesen, dass man XML-Dateien manipulieren kann?**

*Ich habe es nur aus theoretischer Sicht bewiesen, aber nicht praktisch gezeigt.*

---

**Habe ich erklärt wie man XML-Dateien manipulieren kann?**

*Ich habe, dass XML-File dargestellt und erklärt, was passiert. Dabei habe ich ziemlich deutlich mit dem XML-Code dargestellt, welcher Teil implementiert wurde und wieso es diese Auswirkungen hat.* 

---

**Habe ich Lösungsansätze für diese Sicherheitslücken präsentiert?**

*Die Sicherheitslücken habe ich relativ stumpf aufgeschrieben, da die Sicherheitslücke auch relativ stumpf scheint. Die Sicherheitslücke ist vorhanden, aber einfach zu beheben.*