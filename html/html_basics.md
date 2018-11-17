HTML Basics
=============
# TODO

 - [ ] Pünktli bei Ordnern und Files
 - [ ] Absolute und Relative Pfade
 - [ ] Konsole erklären
 - [ ] Htdocs erklären
 - [ ] MAMP erklären

# Grundlagen

Als Nachschlagewerke verwendet ihr am besten developer.mozilla.org. Dort könnt ihr für HTML, CSS aber auch später für CSS und Javascript alles nachlesen, was ihr wissen müsst.

# HTML Dateien
HTML Dateien sind einfache Textdateien, welche mit so genanntem Markup gefüllt ist.

Grundgerüst einer HTML Datei:

	<!DOCTYPE html>
	<html lang="de">
	<head>
	  <meta charset="UTF-8">
	  <title>Dokumenten Titel</title>
	</head>
	<body>
		Euer Code gehört kommt hierhin
	</body>
	</html>


## Tags
HTML verwendet so genannte Tags um zu definieren, um welche Art von Content es sich handelt. Mit Tags könnt ihr dem Browser z.B. Mitteilen, ob es sich bei eurem geschriebenen Text um einen Absatz, einen Titel oder eine Fussnote handelt.

Hier ein paar Beispiele für Tags

	<h1>Ich bin ein titel</h1>
	<p>Ich bin ein Absatz</p>
	<a href="http://www.google.ch>Ich bin ein Link</a>
	<img src="katze.jpg" alt="Ich bin ein Katzenbild">


### Verschachtelung
Die Meisten HTML Tags tauchen Paarweise auf, was soviel bedeutet wie sie haben ein öffnendes und ein schliessendes Element. Zwischen dem öffnenden und schliessenden HTML-Tag kann Text, aber auch weitere HTML Elemente vorkommen. Der Browser unterscheidet dabei das öffnende und das schliessende Element durch den "Slash" (`/`) nach dem "kleiner als"-Zeichen (`<`).

	<div>
		<h1>Ich bin eine Überschrift</h1>
		<p>
			Hier ist ein Absatztext
			<img src="bild.jpg" alt="Ich bin ein Bild">
			<a href="seite.html>Ich bin ein Link im Absatz</a>
		</p>
	</div>

Die oben dargestellten Elemente sind ineinander verschachtelt. Man sagt also, der Link befindet sich innerhalb des Absatzes, welcher sich wiederum in einem Div befindet.

**Wichtig**: Wenn die schliessenden Elemente fehlen, meldet der Browser keinen Fehler, sondern versucht, die Struktur so gut wie möglich Umzusetzen. Dies hat aber meistens unbeabsichtigte Effekte zur Folge, weshalb ihr immer die Tags korrekt schliessen müsst.

### Attribute

HTML Tags können mit zusätzlichen Informationen versetzt werden. Diese nennt man Attribute. Attribute befinden sich immer innerhalb des ersten Tags, eines Tag-Paares. Je nach HTML-Element sind unterschiedliche Attribute möglich. Es gibt einige Attribute, wie z.B. `id` welche auf alle HTML Tags anwendbar sind.

| Attribut | Bedeutung |
|--|--|
| href="seite1.html" | Definiert beim Anker-Tag, wohin der Link führen soll |
| src="bild1.jpg" | Definiert bei einem IMG-Tag, wo der Browser das anzuzeigende Bild findet |
| id="name" | Definiert bei jedem Element eine Eindeutige Identität, mit welcher das Element angesprochen werden kann |
| alt="Text" | Defineirt bei einem IMG-Tag einen alternativen Text, welcher angezeigt wird, wenn das Bild nicht geladen werden konnte |


### Grundlegende TAGs eines HTML Dokumentes

| Tag | Bedeutung |
|--|--|
| `<!DOCTYPE html>` | Die Doctype Präambel befindet sich immer am Anfang eines HTML Dokumentes. Sie teilt dem Browser mit, dass es sich beim Markup um Modernen HTML Code handelt, und der Browser keine Kompatibilitätseinstellungen für ältere HTML Vesionen verwenden soll  |
| `<html>` | Das `<html>`-Element repräsentiert, dass Wurzel Element eures Markups. Es handelt sich dabei also um das oberste Element. Sämtliche anderen Tags, `<!DOCTYPE html>` ausgenommen, müssen sich innerhalb des HTML-Tag befinden |
| `<head>` | Das `<head>`-Element definiert den Kopfteil eures Elements. Markup welches im Head des Dokumentes definiert werden, sind im Browserfenster nicht sichtbar. Im Head werden dem Browser unterschiedliche Informationen übergeben wie z.B. den Seitentitel aber auch die URLs von CSS und Javascript Dateien |
| `<meta charset="UTF-8">` | Definiert die Zeichenencodierung eures HTML Elements. Ist dieses Tag nicht vorhanden, so werden Umlaute wie z.B. äöu falsch dargestellt. Muss im `<head>` vorkommen |
| `<title>` | Definiert den Titel der Webseite. Dieser wird je nach Browser entweder oben am Browser oder am Tab angezeigt. Muss im `<head>` vorkommen |
| `<body>` | Beinhaltet euren Content. Sämtliche Tags welche sich im `<body>` befinden, sind im Browserfenster sichtbar |

#### Überschriften


#### Zeilenumbruch
Wenn ihr in eurem HTML Code einen gewöhnlichen Zeilenumbruch macht, ist dieser auf der Webseite nicht ersichtlich. Dem Browser ist es insofern egal, wieviele Spaces und Zeilenumbrüche ihr in eurem HTML Markup macht. Soll innerhalb des Textes ein Umbruch erscheinen, so musst du den `<br>` Tag verwenden.

	Ich bin eine Zeile<br>
	Ich erscheine auf der nächsten Zeile<br>
	Und ich auf der dritten Zeile<br>

**Wichtig:** `<br>` sollte nicht missbraucht werden, um Abstände zwischen Elementen zu erzeugen. Dazu soll `margin` und `padding` von CSS verwendet werden.

#### Absatz

	<p>Ich bin ein Textabsatz</p>
	<p>Ich bin ein weiter Textabsatz</p>

#### Kommentare

	<!-- Ich bin ein Kommentar -->

#### Textformatierung

##### Fett


##### Italic


#### Bilder
	<img src="katze.jpg" alt="Ich bin ein Katzenbild">

#### Links
Eines der ursprünglichsten HTML-Elemente ist das Anchor Element. Es ermöglichte bereits seit Beginn des Internets das Erstellen von Links in und zwischen wissenschaftlichen Publikationen. Mit Links könnt ihr von einer HTML Seite auf eine andere verweisen. Dabei könnt ihr auf eure eigene Seiten verweisen, aber auch auf jede andere Webseite verweisen.

**Beispiel eines Links:**

	<a href="http://www.google.ch">Ich bin ein Link zu Google</a>
	<a href="seite2.html>Ich bin ein relativer Link zu Seite 2</a>
	<a href="/seite1.html>Ich bin ein absoluter Link zu Seite 2</a>

Mit dem Attribut `href` definierst du, wohin der Link zeigen soll. Als `href` kannst du absolute URLs (`/seite1.html`), URLs zu anderen Webservern (`http://www.google.ch`) oder auch relative URLs (`seite2.html`) angeben.

##### Links mit Target
Bei einem Link kannst du definieren, wie die neue Seite geöffnet werden soll. Dafür kannst du das `target` Attribut angeben.

	<a href="seite2.html target="_blank">Seite 2 als neues Tab</a>

Bei Browsern ohne Tabs, öffnet `target="_blank"` ein neues Fenster.
|Target| Effekt |
|--|--|
| _self | Öffnet die Seite im selben Fenster. (Standard verhalten) |
| _blank | Öffnet die Seite in ein neues Fenster bzw. einen neuen Tab |

Nebst `_blank` gibt es noch weitere Möglichkeiten wie `_parent`, `_top` und `_self` welche in Designs mit Framesets verwendet werden. Da Framesets aber heute kaum mehr verwendet werden, werden wir diese nicht behandeln.


Wie

#### Listen
##### Sortierte Liste
#### Unsortierte Liste

#### Tabellen
	<table>
		<tr>
			<td>Zelle 1, Reihe 1</td>
			<td>Zelle 2, Reihe 1</td>
		</tr>
		<tr>
			<td>Zelle 1, Reihe 2</td>
			<td>Zelle 2, Reihe 2</td>
		</tr>
	</table>
##### Spalten verbinden
	<table>
		<tr>
			<td>Zelle 1, Reihe 1</td>
			<td>Zelle 2, Reihe 1</td>
			<td>Zelle 3, Reihe 1</td>
		</tr>
		<tr>
			<td>Zelle 1, Reihe 2</td>
			<td colspan="2">Zelle 2, Reihe 2</td>
		</tr>
	</table>

##### Tabellen Überschriften
	<table>
		<thead>
			<tr>
				<th>Vorname</th>
				<th>Nachname</th>
			</tr>
		</thead>
		<tbody>
			<tr>
				<td>Rolf</td>
				<td>Eggenberger</td>
			</tr>
		</tbody>
	</table>

#### Formulare

	<form action="input_text.htm" method="post">
	     <label for="vorname">Vorname:</label><br>
	     <input id="vorname" name="vorname" type="text" size="30" maxlength="30">

	     <label for="nachname">Nachname:</label><br>
	     <input id="nachname" name="nachname" type="text" size="30" maxlength="40">

		<button>Absenden</button>
	</form>

##### Text Elemente

##### Select

##### TextArea

##### Button

### Semantische Elemente (HTML5)
| Tag | Beschreibung |
|--|--|
| header |  |
| nav |  |
| aside |  |
| footer |  |
| main |  |
| article |  |
| section |  |

### Euer Webserver

#### Gute Ordnerstrukturen

#### Localhost

#### MAMP




