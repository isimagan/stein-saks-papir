# Stein, saks, papir
Vi skal nå programmere micro:biten til å spille stein, saks, papir med deg.

## Før du starter
Fjern ``||basic:ved start||``- og ``||basic:gjenta for alltid||``-blokkene

## Steg 1
Vi begynner med å lage en variabel som vi kaller ``||variables:bildenummer||``

## Steg 2
Sett inn en ``||input:når ristes||``-blokk. Alt som skjer frem til ekstraoppgavene skal skje inni denne blokka.
``` blocks
input.onGesture(Gesture.Shake, function(){
})
```

## Steg 3
Nå skal vi definere variabelen vår. Da skal vi sette inn ``||variabels:sett bildenummer til 0||``
``` blocks
input.onGesture(Gesture.Shake, function(){
    bildenummer = 0
})
```

## Steg 4
``||variabel:bildenummer||`` skal være et tall mellom 1 og 3. Da må vi først gå inn på Matematikk, finne ``||math:velg tilfeldig mellom 0 og 10||`` og sett den inn i stedet for 0-tallet.
``` blocks
input.onGesture(Gesture.Shake, function(){
    bildenummer = randint(0, 10)
})
```

## Steg 5
Men det tilfeldige tallet skulle være mellom 1 og 3. Bytt ut 0 og 10 med 1 og 3.
``` blocks
input.onGesture(Gesture.Shake, function(){
    bildenummer = randint(1, 3)
})
```

## Steg 6
Nå begynner vi med det som skal skje på micro:biten. Det første som skal skje er å vise hvilket tilfeldig tall ``||variables:bildenummer||`` er blitt.
Begynn med å sette inn ``||basic:vis tall||``

``` blocks
input.onGesture(Gesture.Shake, function(){
    bildenummer = randint(1, 3)
    basic.showNumber(0)
})
```

## Steg 7
Bytt ut ``||basic:0||``-tallet med ``||variables:bildenummer||``
``` blocks
input.onGesture(Gesture.Shake, function(){
    bildenummer = randint(1, 3)
    basic.showNumber(bildenummer)
})
```

## Steg 8
Nå skal vi sette inn en ``||logic:hvis||``-blokk.
Velg da blokken ``||logic:hvis sann så||`` fra logikk.
``` blocks
input.onGesture(Gesture.Shake, function(){
    bildenummer = randint(1, 3)
    basic.showNumber(bildenummer)
    if (true) {}
})
```

## Steg 9
Gå tilbake til logikk og finn ``||logic:0 = 0||``. Sett inn denne i stedet for ``||logic:sann||``
``` blocks
input.onGesture(Gesture.Shake, function(){
    bildenummer = randint(1, 3)
    basic.showNumber(bildenummer)
    if (0 == 0) {}
})
```

## Steg 10
Bytt ut første ``||logic:0||`` med ``||variabel:bildenummer||``, og den andre med ``||logic:1||``.
``` blocks
input.onGesture(Gesture.Shake, function(){
    bildenummer = randint(1, 3)
    basic.showNumber(bildenummer)
    if (bildenummer == 1) {}
})
```

## Steg 11
Hvis ``||variable:bildenummer||`` er 1 betyr det at micro:biten har valgt stein. Sett inn ``||basic:vis skjerm||`` og tegn en stein.
Din stein må ikke være lik denne.
``` blocks
input.onGesture(Gesture.Shake, function(){
    bildenummer = randint(1, 3)
    basic.showNumber(bildenummer)
    if (bildenummer == 1) {
        basic.showLeds(`
            . . . . .
            . # # # .
            . # # # .
            . # # # .
            . . . . .
            `)
    }
})
```

## Steg 12 @showdialog
Nå mangler vi saks og papir. Sett inn to ``||logic:hvis||``-blokker.
Hvis bildenummer er 2 er saks valgt, og hvis den er 3 er papir valgt.
Når det gjelder saks så kan du enten tegne selv eller velge saks-ikonet.
``` blocks
basic.showIcon(IconNames.Scissors)
```
### Husk
I eksempelet over står det ``||basic:ved start||``. Ikke bruk den.

## Klarte du det? @showhint
Hvis du klarte det så ser det kanskje slik ut?
``` blocks
input.onGesture(Gesture.Shake, function () {
    bildenummer = randint(1, 3)
    basic.showNumber(bildenummer)
    if (bildenummer == 1) {
        basic.showLeds(`
            . . . . .
            . # # # .
            . # # # .
            . # # # .
            . . . . .
            `)
    }
    if (bildenummer == 2) {
        basic.showIcon(IconNames.Scissors)
    }
    if (bildenummer == 3) {
        basic.showLeds(`
            . . . . .
            . # # # .
            . # # # .
            . # # # .
            . # # # .
            `)
    }
})
```
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("https://makecode.microbit.org/", "isimagan/stein-saks-papir");</script>