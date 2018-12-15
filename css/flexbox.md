Flexbox
=====

# Grundlegendes

## Aufbau
<img src="assets/flexbox/container.svg" style="max-width: 400px;">

<img src="assets/flexbox/items.svg" style="max-width: 400px;">

Bei Flexbox gibt es jeweils ein Container Element, welches die `display`-Eigenschaft `flex` haben muss. Innerhalb des Container Elements, befinden sich die Items. Die möglichen CSS-Eigenschaften für Container und Items sind unterschiedlich:

### Container Eigenschaften
* display
* flex-direction
* flex-wrap
* flex-flow
* justify-content
* align-items
* align-content

### Item Eigenschaften
* order
* flex-grow
* flex-shrink
* flex-basis
* flex
* align-self




## Achsen

Ein Flexbox Container hat zwei Achsen. Die Hauptachse, auch "Main Axis" genannt, sowie die Querachse, auch "Cross Axis" genannt.

### Normale Achsen

<img src="assets/flexbox/direction.png" style="max-width: 400px;">

Die Elemente innerhalb des Containers werden längs der Hauptachse positioniert. Dadurch sind sie Standardmässig nebeneinander.

### Gedrehte Achsen

<img src="assets/flexbox/direction_rotated.png" style="max-height: 400px;">

Durch die CSS-Eigenschaft `flex-direction` werden die Hauptachse und die Querarchse um 90° gedreht. Die Elemente werden weiterhin an der Hauptachse positioniert. Dadurch wären die Elemente innerhalb des Containers nun untereinander.



# Container Eigenschaften

## Display

Flexbox aktivierst du, indem du auf deinem Container-Element die Display property auf Flex setzt.

Standardmässig sind Block-Elemente untereinander. Sobald du auf Container Flexbox aktivierst, rutschen die Elemente nebeneinander. Dies passiert, weil `flex-direction` Standardmässig auf `row` gesetzt ist.

<img src="assets/flexbox/display.gif" style="max-width: 600px;">

HTML

    <div class="container">
      <div>1</div>
      <div>2</div>
      <div>3</div>
      <div>4</div>
    </div>
CSS

    .container {
      display: flex;
    }

## Flex-direction

### Row vs Column

<img src="assets/flexbox/direction.gif" style="max-width: 600px;">

Mit `flex-direction` definierst du die Richtung der Elemente innerhalb des Containers auf der Hauptachse

### Reverse

<img src="assets/flexbox/direction-reverse.gif" style="max-width: 600px;">

Wenn du die Reihenfolge der Elemente umgekehren willst, kannst du `column` und `row` mit `-reverse` ergänzen.

## justify-content

<img src="assets/flexbox/justify-content.gif" style="max-width: 600px;">

Mit `justify-content` richtest du die Elemente innerhalb des Containers an der Hauptachse aus.


Wert | Effekt
---------|----------
flex-start | Die Elemente werden alle direkt nebeneinander positioniert. Das erste Element beginnt links, bzw oben an der Hauptachse. Falls die `flex-direction:` umgedreht wurde, beginnt es entweder rechts oder unten.
flex-end | Die Elemente werden alle direkt nebeneinander positioniert. Das erste Element beginnt rechts, bzw unten an der Hauptachse. Falls die `flex-direction:` umgedreht wurde, beginnt es entweder links oder oben.
space-around | Macht links und rechts von jedem element den gleichen Abstand. Da dies links und rechts passiert, gibt es zwischen den Elementen doppelt soviel Abstand wie neben den Elementen am Rand.
space-between | Macht zwischen allen Elementen, die sich nicht am Rand befinden, einen gleichmässigen Abstand. Die Elemente am Rand haben keinen Abstand zum Rand.
space-evenly | Macht zwischen allen Elementen einen gleichmässigen Abstand.
center | Zentriert alle Elemente in der Hauptachse.


## flex-wrap

    flex-wrap: nowrap | wrap | wrap-reverse


Standardmässig versucht der Browser, alle Flex Items auf einer Zeile darzustellen.

Um den Umbruch von Elementen zu erlauben, musst du die `flex-wrap` property setzen. Standardmässig ist die Eingenschaft auf `nowrap`gesetzt.
### Nicht umbrechen (Nowrap)
<img src="assets/flexbox/nowrap.png">

    .container {
      flex-wrap: nowrap;
    }

### Umbrechen (Wrap)

<img src="assets/flexbox/wrap.png">

    .container {
      flex-wrap: wrap;
    }

### Von unten mmbrechen (Wrap reverse)

<img src="assets/flexbox/wrap-reverse.png">

    .container {
      flex-wrap: wrap-reverse;
    }

## flex-flow

Ist eine Abkürzung um `flex-direction` und `flex-wrap` auf einmal zu setzten.

### Aufbau
Als erstes Argument gebt ihr die `flex-direction` an und als zweites Argument die `flex-wrap`-Eigenschaft.

    flex-flow: <flex-direction> || <flex-wrap>

### Beispiele

    flex-flow: row-reverse wrap
    flex-flow: row nowrap
    flex-flow: column-reverse wrap-reverse


## align-items

Definiert, wie die Elemente pro Zeile in der Querachse positioniert werden.

<img src="assets/flexbox/align-items.gif" style="max-width: 600px;">

Wert | Beschreibung
-------- | --------
flex-start | Element ist positioniert am Anfang der Querachse
flex-end | Element ist positioniert am Ende der Querarchse
center | Element wird in der Querachse zentriert
baseline | items are aligned such as their baselines align
stretch (default) | stretch to fill the container (still respect min-width/max-width)

## align-content

<img src="assets/flexbox/align-content.svg" style="max-width: 400px">

Mit `align-content` definierst du, wie die Items in der Querarchse positioniert werden.

**Wichtig**: Diese Eigenschaft hat nur einen Effekt, wenn es mehr als eine Zeile von Items hat.

Wert | Beschreibung
-------- | --------
flex-start | Alle Items werden am beginn der Querachse positioniert und sind so nahe wie möglich beieinander.
flex-end | Alle Items werden Ende der Querarchse positioniert und sind so nahe wie möglich beieinander.
center | Die Elemente werden in der Mitte der Querachse positioniert und sind so nahe wie möglich beieinander.
space-between | lines evenly distributed; the first line is at the start of the container while the last one is at the end
space-around | lines evenly distributed with equal space around each line
stretch (default) | lines stretch to take up the remaining space

# Item Eigenschaften

## order

<img src="assets/flexbox/order.svg" style="max-width: 400px">

Normalerweise werden die Elemente innerhalb des Flex Containers in der gleichen Reihenfolge positioniert, wie sie im HTML vorkommen. Mit der `order` Einschaft, kannst du die Reihenfolge beeinflussen. Der Standart-Wert der Reihenfolge ist `0`.

    .item {
        order: <integer>; /* Standard ist 0 */
    }


## flex-basis

Definiert die Grösse des Elementes, bevor der verbleibende Platz unter den Elementen verteilt wird. Als Wert wird eine Länge (20%, 10rem, 10px) oder das Keywort `auto` angegeben. Wird `auto` verwendet, beachtet der Browser die `width` bzw. `height` Eigenschaft des Elementes.

    .item {
        flex-basis: <length> | auto; /* Standard ist auto */
    }

### flex-basis 0

<img src="assets/flexbox/base_zero.svg">

Wird `flex-basis: 0` gesetzt, so wird der Platz rechts und links vom Inhalt bei der Grösse nicht beachtet. Wird `flex-basis: auto` gesetzt, wird der verfügbare Platz zwischen den Elemente basierend auf ihrer `flex-grow` Eigenschaft verteilt.
## flex-grow

Definiert ob das Element innerhalb des Flex Containers wachsen kann. Der angegebene Wert wird ohne Masseinheit angegeben, da es sich um eine Proportionsangabe handelt. Ein Elemente mit `flex-grow: 2` kann also maximal doppelt so gross werden, wie ein Element mit `flex-grow: 1`.

Wenn alle Elemente `flex-grow: 1` besitzen, wird der übrige Platz gleichmässig verteilt. Standardmässig sind die Elemente auf `flex-grow: 0?` gesetzt. Negative Werte sind nicht gültig.

    .item {
        flex-grow: 2; /* Standard ist 0 */
    }


## flex-shrink

Definiert ob das Element innerhalb des Flex Containers schrumpfen kann. Der angegebene Wert wird ohne Masseinheit angegeben, da es sich um eine Proportionsangabe handelt. Negative Werte sind nicht gültig.

    .item {
        flex-shrink: <number>; /* Standard ist 1 */
    }

## flex

Mit `flex` können die Eigenschaften `flex-grow`, `flex-shrink`, und `flex-basis` mit einer einzigen Anweisung gesetzt werden. Die hinteren beiden angaben, also `flex-shrink` und `flex-basis` sind optional. Die Standard Werte sind die gleichen wie bei den einzelnen Eingenschaften, also `0 1 auto` (grow 0, shrink 1, basis auto).

    .item {
        flex: 0 | [ <'flex-grow'> <'flex-shrink'> <'flex-basis'> ]
    }

## align-self

<img src="assets/flexbox/align-self.gif" style="max-width: 600px;">

Mit `align-self` kannst du die positionierung auf der Querachse für ein einzelnes Element überschreiben.

    .item {
        align-self: auto | flex-start | flex-end | center | baseline | stretch;
    }

Wert | Beschreibung
---------|----------
 auto | Element wird anhand der `align-items` Eigenschaft definiert
 flex-start | Element wird am Anfang der Querarchse positioniert
 flex-end | Element wir dam Ende der Querachse positioniert
 center | Element wird in der Mitte der Querarchse positioniert
 baseline | TODO
 stretch | Das Element nimmt die maximal verfügbare Höhe bzw. Breite auf der Querachse auf.

# Holy Grail Layout mit Flexbox

Das Beispiel für das Holy Grail Layout mit Flexbox findest du auf [Codepen](https://codepen.io/chriscoyier/pen/vWEMWw).