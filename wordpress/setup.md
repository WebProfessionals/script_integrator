CMS Grundlagen
==============

Mit einem CMS (Content Management System), können gemeinsam Inhalte erstellt und angepasst werden. Es ermöglicht es jemandem eine Webseite anzupassen, ohne über HTML & CSS Kentnisse zu verfügen.

In einem CMS werden sämltiche Inhalte in einer Datenbank gespeichert. Als Inhalte sind Text, Bilder, Videos und auch andere Dateien möglich. Die Menus zwischen einzelnen Seiten können automatisch generiert werden.

Euer Design müsst ihr nur einmal definieren, für jede neu erstellte Seite, kann das gleiche Design angewendet werden. Dadurch muss nur noch der Inhalt gepflegt werden. Beim Aufruf der Seite werden das Design und der dazugehörige Inhalt dann automatisch zusammengeführt.

# Aufbau

Die meisten CMS Systeme sind ähnlich aufgebaut:

## Core

Der Core bietet die Kernfunktionalitäten des CMS an, welche häufig in Frontend / und Backend aufgeteilt sind. Die gesamte Inhaltsverwaltung gehört ebenfalls zum Core.

Am Core ändert ihr selbst nichts, diesen übernehmnt ihr einfach von Wordpress.

## Plugins

Mit Plugins könnt ihr zusätzliche Funktionalitäten zu eurem CMS hinzufügen. Bspw. Facebook Shares, Shop integrationen, Kommentar funktionen, etc. Für Plugins gibt es einen sehr umfangreichen App-Store.

Mit Plugins könnt ihr sehr schnell sehr viel Funktionalität umsetzen. Leider gibt es aber auch Plugins, die untereinander Probleme verursachen oder nicht all zu gut umgesetzt sind. D.h. prüft die Plugins die ihr einsetzt zuerst lokal, bevor ihr sie direkt auf die produktive Seite installiert.

## Themes
Mit Themes könnt ihr das aussehen der Seite anpassen. Hier gibt es unterschiedliche Möglichkeiten. Ihr könnt ein bestehendes Theme nehmen und es euren wünschen nach Anpassen oder ihr könnt auch euer ganz eigenes Theme entwickeln.

Für Themes gibt es ebenfalls wieder Stores, in denen Themes gekauft werden können. Beachtet jeweils die Lizenzbedingungen, des jeweiligen Themes bevor ihr es einfach für mehrere Seiten einsetzt, ohne dafür zu bezahlen.

## Warum ein CMS?

### Vorteile
* Auch nicht-Techies können Inhalte bearbeiten
  ** Dadurch wird der Webmaster (z.B. ihr selbst) entlastet
* Viele Funktionalitäten bereits vorhanden (Suche, RSS Feeds, Bildergalerie,…)
* Mehrere Autoren können gleichzeitig an der Seite arbeiten
* Benutzer/ Rechteverwaltung
* Konsistentes Aussehen der Seiten dank Template/Theme
### Nachteile
* Einarbeitung für Webmaster
* Templating zeitaufwändig
* Benötigt Datenbank und PHP-fähigen Server
* evtl. Performance, Sicherheit

# Opensource vs Enterprise CMS

## Opensource
* Opensource CMS sind in der Regel kostenlos
* Support: Foren und Blogs, man kann aber nicht erwarten, dass einem geholfen wird sondern muss sich meist selbst zu helfen wissen
* Haben Online sehr viel Nachschlagewerke, Stackoverflow Posts und weitere hilfen
* Es gibt sehr viele Plugins und Themes, mit denen das CMS angepasst werden kann

## Enterprise CMS
* Meistens kostenpflichtig
* Support ist durch den Hersteller gewährleistet
* Erweiterte Funktionalität
* * Multi Language / Multi Domain
* * Erweiterte Publishing Workflows (Veröffentlichung, Timing, Freigaben, Einstellungen)
* * Integrierte Rechteverwaltung, z.B. mit Microsoft Active Directory integration

Die Opensource Lösungen sind mittlerweile aber sehr gut und haben Dank ihrer sehr grossen beliebtheit und Community schon sehr viele Funktionalitäten von Enterprise CMS Lösungen übernommen, weshalb häufig auf teure Enterprise Lösungen verzichtet werden kann.

Wichtige Entscheidungsmerkmale zwischen Enterprise oder Opensource CMS Lösungen sind:

### Entscheidungshilfen
* Erwartete Site-Grösse (Anzahl Einzelseiten, Anzahl Bilder / Medien)
* Mehrsprachigkeit unterstützt?
* Multi-Site-Fähigkeit? (Mehrere Websites mit einem CMS verwalten)
* Kosten (Lizenzkosten / TCO)
* * Kann der Kunde überhaupt für die Lizenzkosten aufkommen?
* Skalierbarkeit (Besucherzahl / Traffic)
* * Wieviele Benutzer erwarten wir? 100, 1000, 10000, 100000 pro Tag?
* Benötigte Server-Infrastruktur
* Anzahl Autoren
* Support Ansprüche (Community / Kommerzieller Support)

CMS Lösungen:

## Self Hostet CMS
Diese CMS variationen könnt ihr selbst auf einem Server installieren. Dadurch habt ihr die komplette Kontrolle über die Infrastruktur und die Daten. Manche Kunden (z.B. Banken) müssen ihre Daten aus rechtlichen Gründen in der Schweiz behalten, weshalb ein gehostetes CMS häufig nicht möglich ist.

Die meisten CMS könnt ihr selbständig auf einen Server euerer Wahl installieren:

* Drupal
* Wordpress
* Concrete 5
* Joomla
* Typo3
* * wird nicht mehr sehr häufig verwendet
* Sitecore
* * Kostenpflichtiges CMS

## Durch Anbieter gehostete CMS

Die Daten liegen auf einem Fremden Server und ihr bezahlt jeweils eine Monats- oder Jahresgebühr an den Betreiber.

* Wordpress(.com)
* * Bei Wordpress gibt es beides, bei der angebotenen Version, müsst ihr euch nicht mehr über Updates oder sonstiges kümmern
* Jimdo
* Wix.com


# Wordpress

Wordpress wurde ursprünglich als Blog entworfen. Mittlerweise gibt es aber auch Custom Post Types wodurch es zu einem vollwertigen CMS wird. Der gesammte Source Code ist Open Source und öffentlich zugänglich.

Ebenfalls gibt es regelmässige Updates zu Wordpress welche neue Features ergänzen und auch Sicherheitslücken schliessen. Letzteres ist bei Wordpress besonders wichtig, da die Sicherheitslücken schnell bekannt werden, sind veraltete Wordpress Installationen eine leichte beute für Hacker und Script kiddies.

## Wann ist Wordpress zu empfehlen?
* Grundlegende HTML / PHP-Skills vorhanden
* Zeit und Motivation den Umgang mit Wordpress zu lernen
* Eigenes Hosting vorhanden
* Projekt lässt sich mit Wordpress "abbilden"
* Zeit regelmässig Sicherheitsupdates zu installieren

## Wann sollte Wordpress nicht verwendet werden?
* Projekt hat viele Custom-Funktionen welche sich nicht mit Wordpress abbilden lassen
* Komplexe Layouts
* Einfache Landing-Pages / Seiten die gar kein CMS benötigen
* Sehr viele parallele Zugriffe erwartet

## Voraussetzungen für Wordpress

* Apache Webserver mit PHP
* Datenbank (MySQL Server)
* mod_rewrite Apache Erweiterung
* * wird für schöne (SEO Konforme) URLs benötigt

# Installationsanleitung Wordpress

## Dateien heruterladen
* Wordpress herunterladen
  * Auf (www.wordpress.org) gehen und auf "Get Wordpress" klicken und es herunterladen
* Die Zipdatei von Wordpress müsst ihr entpacken
* Kopiert alle Datein des Zip Archivs in den `htdocs` Ordner euerer MAMP installation
* Erzeugt einen neuen Ordner genannt `wordpress` und fügt dort die ausgepackten Dateien ein
## Datenbank einrichten
* Datenbank einrichten
* Geht auf http://localhost/phpmyadin/
* Auf der Linken Seite seht ihr die bestehenden Datenbanken
* Im oberen Teil klickt ihr auf Datenbanken und dann auf `Neue Datenbank anlegen`
* Gebt als Namen `wordpress` an
* Wählt als Encodierung im Dropdown `UTF-8-general-ci` aus

## Wordpress konfigurieren
* Geht auf http://localhost/wordpress
* Danach sollte der Konfigurator starten
* Wählt Deutsch als Sprache (Du oder Sie)
* Klickt auf Los Gehts
* Füllt das Formular folgendermassen aus

Feldname | Wert
----------- | -----------
Datenbankname | `wordpress` (Gleich wie im phpmyadmin)
Benutzername  |`root`
Passwort | `root`
Datenbank-Host | `localhost`
Tabellen-Präfix | `wp_` (Einfach so lassen wie es ist)

(Die obigen Angaben sind nur für lokale Installationen gedacht. Bei einem richtigen Hosting, erhaltet ihr diese Angaben vom Hoster.)

* Klickt auf Senden
* Wenn alles klar steht, dann hat die Verbindung zur Datenbank geklappt
* Wenn alles klar ist, klickt ihr auf `Installation durchführen`
* Danach könnt ihr das Formular für eure Webseite ausfüllen:

Feldname | Wert
----------- | -----------
Titel der Webseite | `wordpress` (Gleich wie im phpmyadmin)
Benutzername  | Für euren Administrator Account
Passwort | Wählt hier das Passwort zu eurem Account
E-Mail | Gebt eure E-Mail Addresse ein

* Klickt auf Wordpress installieren
* Jetzt sollte: Installation erfolgeich stehen
* Danach solltet ihr auf http://localhost/wp-admin landen. Auf dieser Seite könnt ihr euch jeweils Einloggen, um in den Admin Bereich eures CMS zu kommen. Zum Login verwendet ihr die vorher eingegeben persönlichen Login Daten.
* Nach erfolgreichen Login landet ihr im Dashboard eurer Wordpress installation