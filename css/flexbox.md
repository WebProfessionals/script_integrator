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
center | Zentriert alle Elemente in der Hauptachse.


## flex-wrap



## flex-flow


## align-items
<img src="assets/flexbox/align-items.gif" style="max-width: 600px;">

## align-content

# Item Eigenschaften

## order

## flex-basis

## flex-grow

## flex-shrink

Basis-Wert 1

## flex

## align-self

<img src="assets/flexbox/align-self.gif" style="max-width: 600px;">


# Holy Grail Layout mit Flexbox

Das Beispiel für das Holy Grail Layout mit Flexbox findest du auf [Codepen](https://codepen.io/chriscoyier/pen/vWEMWw).