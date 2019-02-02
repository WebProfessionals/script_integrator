JavaScript
==========
JavaScript ist nicht zu verwechseln mit Java. JavaScript läuft im Browser, Java jedoch nicht. Der eigentliche Name heisst ECMAScript, "JavaScript" wurde sozusagen als Marketing-Massnahme verwendet.

# Wozu kann man JavaScript einsetzen (im Browser)
- DOM Manipulationen
    - HTML Inhalt ändern
    - HTML Attribute ändern
    - HTML / CSS Styles ändern
- Tracking (z.B. Google Analytics)
- Formular-Eingaben validieren für direktes Feedback
- AJAX (asynchrone Anfragen an den Server, ohne Seite neu zu laden) 

# Grundlagen
- JavaScript ist die Sprache des Browsers
- Javascript ist Case Sensitive (Gross-Kleinschreibung ist relevant)
- JavaScript ist objektorientiert und funktional
- JavaScript ist "loose typed", Variablen haben keine vorab definierten "fixen" Typ. Der Typ ergibt sich aus dem Wert, welchen man zuweist.
- JavaScript will auch auf jeder Zeile mit einem `;` abgeschlossen werden
- JavaScript "ohne Aufsätze" nennt man "Vanilla JavaScript", im professionellen Umfeld verwendet man oft auch JavaScript Frameworks wie Angular, Vue, React, jQuery, uvm.

# Hilfe
Wie auch bei HTML / CSS ist bestimmt https://developer.mozilla.org die beste Anlaufstelle für Hilfe zu allen möglichen Funktionen.

# Einbinden von JavaScript in euer HTML
Heutzutage wird JavaScript fast immer als letztes, vor dem schliessenden `</body>` Tag eingebunden.

    <script src="nameDerDatei.js"></script>

Alternativ kann (meist zu Testzwecken oder in den Übungen) JavaScript auch direkt im HTML programmiert werden. Anstatt dem `src` Attribut schreibt man den JavaScript-Code einfach zwischen dem öffnenden und dem schliessenden `<script>` Tag.

    <script>
        alert('Hallo Welt');
    </script>

Die Funktion `alert` öffnet einen Browser-Fensterchen in welchem eine Nachricht steht, dieses besitzt lediglich einen "OK" Button, mit welchem man das Fensterchen wieder schliessen kann.

**Wichtig:** `alert` blockiert die Ausführung des darunterliegenden JavaScript-Codes.

## HTML im `<head>`
Bindet ihr den `<script>` Tag im `<head>` eures Dokumentes ein, kann es sein, dass dieses die Darstellung des HTMLs verzögert, da der Browser auf die Ausführung des JavaScript-Codes wartet, bevor er die Seite darstellt.

# Eine JavaScript Datei erstellen
Öffnet den Editor (z.B. VisualStudio Code) und erstellt eine Datei mit beliebige Namen und der Endung `.js`

// todo

# Javascript debuggen (Fehler finden)
## Entwickler-Tools
Alle modernen Browser bieten spezielle Tools für Entwickler an, mit welchem die Fehlersuche massiv erleichert wird. Die Entwickler-Tools kennt ihr bereits aus dem HTML/CSS Unterricht, wo wir damit die Struktur unseres HTMLs untersucht haben.

In der Konsole kann man nebst Ausgaben welche man via `console.log` oder `console.error` auch direkt kleine Code-Schnipsel laufen lassen.

    > |

An dieser Stelle, wo der Cursor blinkt, könnt ihr direkt JavaScript programmieren. Drückt ihr dann die ENTER Taste, so wird der Code ausgeführt.

# Unterschiede zu PHP
## Ausgabe (während der Entwicklung)
Anstatt dem PHP Befehl `echo` kann man bei der Entwicklung von JavaScript den Befehl `console.log()` verwenden. Diese Funktion "loggt" in die Konsole der Entwickler-Tools.

Somit ist diese Funktion nicht geeignet dafür, um deinem Webseiten-Besucher Informationen darzustellen, sondern lediglich für dich zur Entwicklung und Überprüfung der Funktionsweise deines Codes.

## Variablen
Variablen werden bei JavaScript nicht mit einem vorangestellten `$` ausgezeichnet.
Um eine Variable zu deklarieren (erstmalige Verwendung), verwendet man das Schlüsselwort `var`.

Bei der weiteren Verwendung der Variable ist dann das Schlüsselwort `var` nicht mehr nötig.

Beispiel:

    var test = 'ich bin ein string';

    alert(test);

### Gültige Zeichen für Variablen
- Buchstaben, Zahlen, Underscore und sogar das $-Zeichen
- Müssen mit Buchstaben beginnen (selten mit $ oder _)
- Case-sensitive (Gross-Kleinschreibung ist relevant)
- Ausserdem gibt es reservierte Wörter, welche ihr nicht als Variablen-Namen verwenden könnt.

`if`, `else`, etc. können nicht als Variablen-Namen verwendet werden.

## Vergleichsoperatoren
Sind identisch wie bei PHP.

    ==      Wertgleich
    ===     Wert & Typengleich
    !=      Ungleich
    >=      Grösser oder gleich
    <=      Kleiner oder gleich
    <       Kleiner
    >       Grösser

## Datentypen
    boolean (true oder false)
    number (Zahlen, egal ob mit Dezimale oder nicht)
    string
    null
    undefined

Wichtigster Unterschied zu PHP ist, dass es nicht einen `integer` und einen `double`, sondern nur einen Datentyp `number` gibt, welcher für beide der obigen Zahlen verwendet wird.

## Zuweisungen


## Strings verketten
Im Gegensatz zu PHP, verkettet man Strings in JavaScript Strings nicht mit einem `.` sondern mit einem `+`.
Zusätzlich steht natürlich aber das `+` Symbol auch für eine Addition.

Ist dabei der jeweils linke Wert eine Zahl, versucht JavaScript zu rechnen. Ist der linke Wert ein String, wird der rechte Wert zu einem String konvertiert.

Beispiel:

    var x = 16 + "Volvo"; // 16Volvo
    var x = 16 + 4 + "Volvo"; // 20Volvo
    var x = "Volvo" + 16 + 4; // Volvo164

# Ausgabe ins HTML
Ein eher veralteter Weg eine Ausgabe ins HTML zu schreiben ist `document.write()`. Dieser Befehl hängt einfach seine Ausgaben innerhalb `<body>` Tags, vor dem schliessenden `</body>` an.

Beispiel:

    document.write('Hallo von Javascript');

Für komplexere und gezieltes Setzen von Informationen in euer HTML Dokument ist `document.write()` jedoch nicht geeignet.

# JavaScript Security
Ein wichtiger Unterschied zu PHP ist, dass JavaScript im Browser läuft. Bei PHP sieht der Benutzer deiner Webseite nur das Ergebnis deines PHP-Codes.
Bei JavaScript kann der Besucher (wenn er will) deinen JavaScript-Code ansehen.

**Du darfst niemals sensitive Informationen wie z.B. Passwörter in deinem JavaScript-Code verwenden!**

# Element Selektoren und Ausgabe über `innerHTML`
Mit dem Befehl `document.getElementById()` kannst du ein HTML-Element welches ein bestimmtes ID-Attribut besitzt "selektieren". Danach kannst du dieses Element manipulieren. Mit `document.getElementById('test').innerHTML` manipulierst du beispielsweise den Inhalt zwischen öffnendem und schliessendem Element-Tag.

Beispiel:

    <div id="yolo"></div>

    <script>
        document.getElementById('yolo').innerHTML = 'ich werde innerhalb des div's ausgegeben';
    </script>

Beispiel (spannender):

    <div id="yolo"></div>

    <script>
    setTimeout(
        function() {
            document.getElementById('yolo').innerHTML = 'ich werde innerhalb des div's ausgegeben';
        }, 2000);
    </script>

Das obige Beispiel verzögert das Setzen des Inhalts um 2000 Millisekunden (2 Sekunden).

# Kommentar
Sind identisch wie bei PHP.

    //      Einzeiliger Kommentar

    /*
        Mehrzeiliger Kommentar
    */

# Globale Variablen
Hier gibt es einen wichtigen Unterschied zu PHP.

Definiert man eine Variable ohne das Schlüsselwort `var` ist diese global gültig. Dies kann teilweise zu Kollisionen führen, wenn z.B. ein Skript welches ihr einbindet (z.B. Google Analytics) eine identische globale Variable definiert.

**Globale Variablen sind nach Möglichkeit zu vermeiden.**

# Funktionen
Der Aufbau der Funktionen ist identisch wie bei PHP. Einziger Unterschied: Es gibt keine optionalen Parameter.

## Gültigkeit der Variablen (Scope)
Ebenfalls unterscheidet sich die Sichtbarkeit von ausserhalb der Funktion definierten Variablen zu PHP.

Während bei PHP ausserhalb einer Funktion definierte Variablen innerhalb der Funktion nicht "sichtbar" sind, ist es bei JavaScript so, dass auf die ausserhalb definierte Variable zugeegriffen werden kann.

Umgekehrt ist es so, dass die innerhalb der Funktion verwendeten Variablen ausserhalb **_nicht_** sichtbar sind.

Beispiel:

    var test = 'hallo';

    function testMitScope() {
        var yolo = 1;
        console.log(test);
    }

    // Funktion aufrufen
    testMitScope();

    console.log(yolo);

    Ausgabe (in Konsole):
    hallo
    undefined

## Verwendung von Hochkommas / Escapen

Verwendest du innerhalb eines Strings das selbe Zeichen, wie du für den Start des Strings benutzt hast (also `"` oder `'`), so gibt es einen Fehler, da der String vorzeitig abgeschlossen wird. Um die Wirkung des `"` oder `'` innerhalb eines Strings zu "deaktivieren", muss man diese Zeichen *escapen*. Dies geschieht, indem man unmittelbar vor dem Zeichen einen Backslash `\` schreibt.

    var test = "Alles ist 'ok'"; // Funktioniert
    
    var test = 'Alles ist "ok"'; // Funktioniert

    var test = 'Nichts ist 'ok''; // Fehler

    var test = 'Alles ist \'ok\''; // Funktioniert, da escaped

Gängige Escape Anwendungen

Einfaches Hochkomma escapen

    \'

Doppeltes Hochkomma escapen

    \"

Wenn du einen Backslash verwenden willst, der das darauffolgende Zeichen nicht escaped

    \\

Zeilenumbruch in einem Textfeld (z.B. `<textarea></textarea>`)

    \n

## If / Else

Im Allgemeinen funktionieren `if` `else` und `else if` genau gleich wie bei PHP, jedoch darf `else if` niemals zusammen geschrieben werden (bei PHP funktioniert sowohl `elseif` und `else if`)

Beispiel

    if (zahl === 5) {
        console.log('Ha, die Zahl ist fünf');
    } else {
        console.log('Verflixt, die Zahl ist nicht fünf');
    }

UND Verknüpfung

    &&

ODER Verknüpfung

    ||

Zusätzlich kann man mit Klammern die Bedingungen bzw. die Verknüpfungen zwischen den Bedingungen abgrenzen.

    if (modell === 'A8' && (marke === 'Audi' || marke === 'Opel')) {
        // Code goes here
    }

## Switch / Case

Funktionieren bei JavaScript identisch wie bei PHP.

## Schleifen

### for

Funktioniert gleich wie bei PHP, jedoch muss `var` anstatt `$` geschrieben werden.

    for (var i = 0; i < 5; i++) {
        // Codeblock wird 5x ausgeführt
    }

### while 

Funktionieret gleich wie bei PHP.

    var counter = 0;
    while (counter < 5) {
        // Codeblock wird 5x ausgeführt

        counter++;
    }

**Achtung: Endlos Schleifen im Browser lassen das Tab abstürzen**

### do / while

Funktioniert im Allgemeinen ähnlich wie eine `while` Schleife. Der Unterschied besteht darin, dass eine `do / while` Schlaufe mindestens einmal ausgeführt wird, bevor die Abbruch-Bedingung geprüft wird.

Beispiel

    var counter = 100;
    do {
        console.log('hello there');
    } while (counter < 100);

    // Gibt 'hello there' in der Konsole aus

## Arrays

### Definition
Bei JavaScript ist die Definition eines Arrays identisch wie bei PHP, man deklariert eine Variable und befüllt es dann mittels der eckigen Klammern.

Diese Syntax kennt ihr ja bereits.

Beispiel

    var cars = ['Porsche', 'Volvo', 'Audi'];

**Hauptunterschied ist, dass JavaScript keine assoziativen Arrays kennt**

### Elemente ins Array einfügen
Um am Ende des bereits definierten Arrays ein weiteres Element einzufügen, kann an die Funktion `Array.push()` verwenden.

*Array* im obigen Code-Schnipsel steht dabei für den Variablen-Namen des Arrays.

Beispiel

    var cars = ['Porsche'];

    cars.push('Volvo');

    console.log(cars);

    Ausgabe:
    (2) ["Porsche", "Volvo"]


### Array Länge ermitteln (Anzahl der Elemente im Array)
Bei PHP konnten wir jeweils `count()` verwenden, um die Anzahl der Elemente welche sich in einem Array befinden zu ermitteln. Bei Javascript gibt es die Funktion `Array.length`.

*Array* im obigen Code-Schnipsel steht dabei für den Variablen-Namen des Arrays.

Beispiel

    var cars = ['Porsche'];
    
    console.log(cars.length);

    Ausgabe:
    1

Weiteres Beispiel

    var persons = [];
    console.log(persons); // 0

    persons.push('Pascal');
    console.log(persons.length); // 1

    persons.push('Hugo');
    console.log(persons.length); // 2

*Hinweis: Bei den meisten Entwickler-Tools kann man nach dem man ein Array mitteels `console.log()` ausgegeben hat den Inhalt "aufklappen" (mit dem Pfeilchen). Dies ist sehr nützlich um sich einen Überblick zu verschaffen.*

## DOM (Document Object Model)

Das DOM repräsentiert die Struktur des HTML Dokumentes als Baumstruktur. Der Haupt-Knoten (document) liegt dabei zuoberst, im Dokument verschachtelte Elemente liegen in Unterknoten.

Dieser Baum wird vom Browser im Hintergrund aufgebaut, nachdem die HTML-Seite komplett geladen ist.

### window
Repräsentiert das Browser-Fenster.

### document
Repräsentiert das HTML-Dokument (die Webeseite an sich).

Alles was du innerhalb deines HTML Dokuments an Tags schreibst, befinden sich dann unterhalb des `document`s. Typischerweise hat ja jedes HTML Dokument einen öffnendes und schliessendes `<html>` Element, ein `<head>` Element und ein `<body>` Element.

Willst du nun aus dem JavaScript mittels DOM auf den Body zugreifen, würdest du folgendes schreiben:

    document.body.innerHTML = 'Ich werde in den Body geschrieben';
    
### DOM Selektoren
Obige Art auf Elemente zuzugreifen wäre bei weit verschachtelten Strukturen sehr umständlich bzw. nahezu unmöglich. Deshalb stellt uns DOM sogenannte Selektoren zur Verfügung.

#### document.getElementById()
Selektiert ein Element welche eine bestimmte ID besitzt.

Beispiel:

    <div id="demo"></div>

    <script>
    document.getElementById('demo').innerHTML = 'Hellouuuu!';
    </script>

Moderne Selektoren sind flexibler einsetzbar und haben die Syntax, welche ihr vom Schreiben der CSS-Selektoren kennt, übernommen.

#### document.querySelector()
Bei der `querySelector()` Funktion könnt ihr als Selektor könnt ihr einen beliebigen CSS-Selektor einsetzen.

Also:

    #           IDs
    .           Klassene
    element     Elemente

    ...und beliebige Kombinationen davon

sowie Pseudo-Selektoren wie:

    :first-child()

    :nth-child()

    etc.

Beispiel:

    <div id="demo"></div>

    <script>
        document.querySelector('#demo').innerHTML = 'Hellouuuu!';
    </script>

    Ausgabe:
    <div id="demo">Hellouuuu!</div>

***Wichtig: Es wird dabei immer nur ein Element selektiert***

Das mittels eines DOM-Selektors ausgewählte Element kannst du auch in eine Variable speichern, so dass du bei mehrfachen Manipulationen nur einmal das Element selektieren musst.

Beispiel:
    <div id="demo"></div>

    <script>
        var element = document.querySelector('#demo');

        element.innerText = 'Mein Textchen';
        element.style = 'color: blue;';
    </script>

Du siehst, dass auf den Folgezeilen jeweils anstatt des Selektors einfach die Variable verwendet wird, in welche wir das Element auf der 1. Zeile "abgefüllt" haben.

#### document.querySelectorAll()
Dieser Selektor verhält sich weitestgehend identisch mit `querySelector`, jedoch werden alle zutreffenden Elemente in Form eines Array-ähnlichen Datentypes zurückgegeben.

Beispiel:

    <div id="demo"></div>
    <div class="box"></div>
    <div class="box"></div>

    <script>
        console.log(document.querySelectorAll('.box').length);
    </script>

    Ausgabe:
    2

### Attribute manipulieren
Hast du ein Element erst einmal selektiert, kannst du ALLES möglich damit anstellen. Jedes Attribut, dass du im HTML-Markup schreiben kannst, könntest du auch per DOM Manipulation setzen.

    element.innerHTML              Schreibt Text oder HTML in ein Element
    element.innerText              Schreibt Text in ein Element, HTML wird ausgeschrieben
    element.style                  Setzt Inline-CSS Styles

`element` steht beim obigen Beispiel für ein *vorgängig* per DOM Selektor selektiertes Element.

Beispiel:

    <h1 class="titel">Hallooooo Welt</h1>

    <script>
        var titel = document.querySelector('.titel');
        titel.style = 'color: blue; padding: 20px;';
    </script>

### Attribute von mehreren Elementen manipulieren
Wie oben beschrieben, kannst du mit `querySelectorAll()` mehrere Elemente selektieren.
Um dann jedoch die Attribute dieser Elemente zu verändern, funktioniert folgender Code **nicht** mehr.

Beispiel (funktioniert nicht!!!!):

    <div class="box"></div>
    <div class="box"></div>

    <script>
        document.querySelectorAll('.box').innerText = 'Test';
    </script>

Damit dieser Code die gewünschte Funktion ausführt, musst du jedes selektierte Element in einer Schlaufe durchlaufen und dann auf das jeweils aktuelle Element `.innerText` darauf setzen.

    <div class="box"></div>
    <div class="box"></div>

    <script>
        var elements = document.querySelectorAll('.box');

        for (var i = 0; i < elements.length; i++) {
            elements[i].innerText = 'Test'
        }
    </script>

    Ausgabe:
    <div class="box">Test</div>
    <div class="box">Test</div>

### Style von Elementen manipulieren
In den vorgängigen Beispielen haben wir einfach den kompletten Inline-Style als String gesetzt. Nachteil daran ist, dass mit jeder Änderung der komplette String neu gesetzt werden muss.

Beispiel (suboptimal):
    <div class="box">Textchen</div>

    <script>
        var box = document.querySeletor('.box');
        box.style = 'border: 1px solid red; color: blue;';

        box.style = 'color: red;';
    </script>

    Ausgabe:
    <div style="color: red;">Textchen</div>

Wie du siehst, sind die Styles der ersten Manipulation komplett verloren gegangen.

Wir brauchen also eine besseres Mittel, um einzelne Styles zu setzen.
Mittels `element.style.cssEigenschaft` kannst du gezielt eine CSS-Eigenschaft per Inline-Style setzen. Überschreibst du eine Eigenschaft, ist jeweils nur die definierte Eigenschaft davon betroffen.

**Wichtig: Die restlichen, bereits gesetzten Eigenschaften, bleiben erhalten**

Beispiel:

    <div class="box">Textchen</div>

    <script>
        var box = document.querySeletor('.box');
        box.style.border = '1px solid red';
        box.style.color = 'blue';

        box.style.color = 'red';
    </script>

    Ausgabe:
    <div style="borderr: 1px solid red; color: red;">Textchen</div>

Eigenschaften, welche im CSS einen Bindestrich beinhalten (`border-radius`, `background-color`, etc.) können nicht mittels `element.style.border-radius = '3px';` gesetzt werden, da Bindestriche in diesem Kontext nicht erlaubt sind.
Um trotzdem diese Eigenschaften setzen zu können, wandelt man den Binestrich in einen Grossbuchstaben des auf den Bindestrich folgenden Wortes um.

Aus `border-radius` wird also `borderRadius`.

Diese Schreibweise nennt man "Camel-case", da die Grossbuchstaben an Kamelhocker erinnern.


## Elemente per JavaScript erzeugen

HTML-Elemente kannst du nicht nur in deinem HTML-Dokument erzeugen, sondern auch per JavaScript-Code, nachdem die Seite bereits geladen ist.

Dafür brauchst du zwei Funktionen.
- createElement()
- appendChild()

Mit `createElement()` erstellst du ein Element von beliebigem Typ (`a`, `button`, `h1`, etc.), dieses kannst du wie ein bei den obigen Beispielen selektiertes Element in einer Variable zwischenspeichern
    
    <script>
        var newElement = document.createElement('div');
    </script>

Führst du obigen Code aus, siehst du dein neues Element noch nicht im Browser. Das liegt daran, dass du noch definiert hast wo in deinem DOM-Baum dieses neue Element "eingeklinkt" werden soll.

Dafür brauchst du nun die zweite Funktion, `appendChild()`, damit fügst du das neu erstellte Element am Ende und innerhalb eines anderen Elements ein.
Um also das neu erstellte `<div>` im Body anzuhängen, würdest du folgenden Code benötigen:

    <script>
        var newElement = document.createElement('div');
        document.body.appendChild(newElement);
    </script>

Anstelle von `document.body` kannst du jedes beliebige andere Element verwenden, welches du vorgängig mit einem Selektor ausgewählt hast.

Beispiel:

    <div class="box"></div>

    <script>
        var newElement = document.createElement('h1');
        var zielElement = document.querySelector('.box');
        zielElement.appendChild(newElement);
    </script>

### CSS-Klasse setzen mit `classList`
Ähnlich wie du Styles auf dein Element setzen konntest, kannst du auch CSS-Klassen hinzufügen oder entfernen. Dafür brauchst du `classList`.
`classList` bietet dir unter anderem Funktionen wie `add()` und `remove()` an.

Willst du einem Element also eine CSS-Klasse hinzufügen, machst du das wie folgt:

    <div class="box">box box box</div>

    <script>
        var box = document.querySelector('box');
        box.classList.add('box-special');
    </script>

    Ausgabe:
    <div class="box box-special">box box box</div>

Im Umkehrschluss kannst du Klassen auch wieder entfernen:

    <div class="box box-active">box box box</div>

    <script>
        var box = document.querySelector('box');
        box.classList.remove('box-active');
    </script>

    Ausgabe:
    <div class="box">box box box</div>

**Wichtig: Bei `add()` und `remove()` musst du keinen Punkt vor dem Klassennamen schrieben, da durch den Kontext (Verwendung von `classList`) bereits klar ist, dass es sich beim angegebenen String um eine CSS-Klasse handelt.***
 
### `value`-Attribut
Spannend ist das `value`-Attribut mit welchem du den Wert eines Eingabefeldes "auslesen" kannst.

Beispiel:

    <input type="text" id="demo" value="fixer wert">

    <script>
        var eingabe = document.querySelector('#demo');

        console.log(eingabe.value);
    </script>

    Ausgabe (in Konsole):
    fixer wert

Wie du siehst, kannst du Attribute nicht nur *neu setzen* sondern auch **lesen**;