# Ekstraoppgave 1: Tøm skjermen
Vi skal tømme skjermen når ``||input:A+B||`` trykkes på.
Dette må skje ved siden av det du har gjort.

## Steg 1
Sett inn ``||input:når knapp A trykkes||``, og endre ``||input:A||`` til ``||input:A+B||``
``` blocks
input.onButtonPressed(Button.AB, function(){})
```

## Steg 2
Inni denne blokka setter vi inn ``||basic:tøm skjerm||``.
``` blocks
input.onButtonPressed(Button.AB, function(){
    basic.clearScreen()
})
```
# Ekstraoppgave 2: Startskjerm
Vi vil at når micro:biten starter skal vi vise stein, saks og papir.
Det skal gå et halvt sekund mellom hvert bilde, og du skal bruke samme bilde som du nettopp lagde.

## Steg 1
Sett inn ``||basic:ved start||``. Her viser du stein.
``` blocks
basic.showLeds(`
    . . . . .
    . # # # .
    . # # # .
    . # # # .
    . . . . .
    `)
```

## Steg 2
Under bildet setter du inn ``||basic:pause (ms) 100||``. Husker du hvor mange millisekunder (ms) det er i ett sekund? Hvor mange millisekunder er det da i et halvt sekund?
``` blocks
basic.showLeds(`
    . . . . .
    . # # # .
    . # # # .
    . # # # .
    . . . . .
    `)
basic.pause(500)
```

## Ser det slik ut nå?
Har du satt inn alt skal det nå se slik ut.
``` blocks
basic.showLeds(`
    . . . . .
    . # # # .
    . # # # .
    . # # # .
    . . . . .
    `)
basic.pause(500)
basic.showIcon(IconNames.Scissors)
basic.pause(500)
basic.showLeds(`
    . . . . .
    . # # # .
    . # # # .
    . # # # .
    . # # # .
    `)
```

## Steg 3
Siden dette bare skal skje på starten så må vi huske ``||basic:tøm skjerm||``.
MEN hvis vi setter den inn rett etter siste bilde så vil vi ikke se bildet før skjermen tømmes.
Så vi venter 1 sekund før skjermen tømmes.
``` blocks
basic.showLeds(`
    . . . . .
    . # # # .
    . # # # .
    . # # # .
    . . . . .
    `)
basic.pause(500)
basic.showIcon(IconNames.Scissors)
basic.pause(500)
basic.showLeds(`
    . . . . .
    . # # # .
    . # # # .
    . # # # .
    . # # # .
    `)
basic.pause(1000)
basic.clearScreen()
```
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("https://makecode.microbit.org/", "isimagan/stein-saks-papir");</script>