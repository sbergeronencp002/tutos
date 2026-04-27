# Tutoriel 20 — La fleur lumineuse 🌸

## @showdialog

🎯 **Objectif** : anime une fleur qui pousse… et qui réagit à la lumière grâce au **capteur** du micro:bit !

Dans ce tutoriel, tu vas créer des fonctions pour chaque étape de la vie d'une fleur, et utiliser le **capteur de lumière** du micro:bit pour la faire éclore ou faner selon la luminosité !

C'est parti ! 🚀

## Étape 1 — Préparer l'espace de travail

🧹 Fais le ménage !

➡️ Supprime le bloc ``||basic:toujours||``.

> 💡 On garde le bloc ``||basic:au démarrage||`` — il affichera la graine dès l'allumage !

## Étape 2 — La fonction `graine`

🌱 Le début de la vie !

➡️ Crée une fonction et nomme-la `graine`.

➡️ Glisse un bloc ``||basic:montrer LEDs||`` à l'intérieur — une petite graine repose au sol.

➡️ Ajoute une pause de `500` ms.

```blocks
function graine() {
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . # . .
        . # # # .
        `)
    basic.pause(500)
}
```

## Étape 3 — La fonction `bourgeon`

🌿 La tige pousse !

➡️ Crée une fonction et nomme-la `bourgeon`.

➡️ Un bourgeon fermé apparaît en haut d'une tige. Reproduis le dessin et ajoute une pause de `500` ms.

> 💡 La tige monte depuis le bas — la fleur cherche la lumière !

```blocks
function bourgeon() {
    basic.showLeds(`
        . . # . .
        . # # # .
        . . # . .
        . . # . .
        . . # . .
        `)
    basic.pause(500)
}
```

## Étape 4 — La fonction `fleur`

🌸 La fleur est en pleine floraison !

➡️ Crée une fonction et nomme-la `fleur`.

➡️ Les pétales s'ouvrent en grand — reproduis le dessin et ajoute une pause de `500` ms.

> 💡 La rangée du haut et les côtés forment les pétales — le centre et la tige restent bien visibles !

```blocks
function fleur() {
    basic.showLeds(`
        . # . # .
        # # # # #
        . # # # .
        . . # . .
        . . # . .
        `)
    basic.pause(500)
}
```

## Étape 5 — La fonction `fanee`

🍂 La fleur se fane...

➡️ Crée une fonction et nomme-la `fanee`.

➡️ La tête de la fleur s'incline — reproduis le dessin et ajoute une pause de `500` ms.

> 💡 La tige reste droite, mais la tête penche — comme une fleur privée de soleil !

```blocks
function fanee() {
    basic.showLeds(`
        . # # . .
        # . # . .
        . . # . .
        . . # . .
        . . # . .
        `)
    basic.pause(500)
}
```

## Étape 6 — La fonction `cycle_vie`

✨ La vie de la fleur en une séquence !

➡️ Crée une fonction et nomme-la `cycle_vie`.

➡️ À l'intérieur, appelle successivement : `graine`, `bourgeon`, `fleur`.

> 💡 `cycle_vie` orchestre la croissance de la graine jusqu'à la pleine floraison — sans jamais dessiner elle-même !

```blocks
function graine() {
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . # . .
        . # # # .
        `)
    basic.pause(500)
}
function bourgeon() {
    basic.showLeds(`
        . . # . .
        . # # # .
        . . # . .
        . . # . .
        . . # . .
        `)
    basic.pause(500)
}
function fleur() {
    basic.showLeds(`
        . # . # .
        # # # # #
        . # # # .
        . . # . .
        . . # . .
        `)
    basic.pause(500)
}
function cycle_vie() {
    graine()
    bourgeon()
    fleur()
}
```

## Étape 7 — Bouton A : cycle_vie

➡️ Glisse le bloc ``||input:lorsque le bouton A est pressé||`` dans l'espace de travail.

➡️ À l'intérieur, appelle `cycle_vie`.

```blocks
function graine() {
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . # . .
        . # # # .
        `)
    basic.pause(500)
}
function bourgeon() {
    basic.showLeds(`
        . . # . .
        . # # # .
        . . # . .
        . . # . .
        . . # . .
        `)
    basic.pause(500)
}
function fleur() {
    basic.showLeds(`
        . # . # .
        # # # # #
        . # # # .
        . . # . .
        . . # . .
        `)
    basic.pause(500)
}
function cycle_vie() {
    graine()
    bourgeon()
    fleur()
}
input.onButtonPressed(Button.A, function () {
    cycle_vie()
})
```

## Étape 8 — Bouton B : fanee

➡️ Glisse le bloc ``||input:lorsque le bouton B est pressé||`` dans l'espace de travail.

➡️ À l'intérieur, appelle `fanee`.

```blocks
function fanee() {
    basic.showLeds(`
        . # # . .
        # . # . .
        . . # . .
        . . # . .
        . . # . .
        `)
    basic.pause(500)
}
input.onButtonPressed(Button.B, function () {
    fanee()
})
```

## Étape 9 — Bouton A+B : fleur

➡️ Glisse le bloc ``||input:lorsque le bouton A+B est pressé||`` dans l'espace de travail.

➡️ À l'intérieur, appelle `fleur`.

```blocks
function graine() {
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . # . .
        . # # # .
        `)
    basic.pause(500)
}
function bourgeon() {
    basic.showLeds(`
        . . # . .
        . # # # .
        . . # . .
        . . # . .
        . . # . .
        `)
    basic.pause(500)
}
function fleur() {
    basic.showLeds(`
        . # . # .
        # # # # #
        . # # # .
        . . # . .
        . . # . .
        `)
    basic.pause(500)
}
function fanee() {
    basic.showLeds(`
        . # # . .
        # . # . .
        . . # . .
        . . # . .
        . . # . .
        `)
    basic.pause(500)
}
function cycle_vie() {
    graine()
    bourgeon()
    fleur()
}
input.onButtonPressed(Button.A, function () {
    cycle_vie()
})
input.onButtonPressed(Button.B, function () {
    fanee()
})
input.onButtonPressed(Button.AB, function () {
    fleur()
})
```

## Étape 10 — Capteur de lumière : sombre → fanee

🌑 La fleur réagit à l'obscurité !

➡️ Glisse le bloc ``||input:lorsque (sombre)||`` dans l'espace de travail.

➡️ À l'intérieur, appelle `fanee`.

> 💡 Le micro:bit utilise ses LEDs comme **capteur de lumière** ! Quand l'obscurité est détectée, la fleur se fane automatiquement — comme une vraie plante privée de soleil !

```blocks
function fanee() {
    basic.showLeds(`
        . # # . .
        # . # . .
        . . # . .
        . . # . .
        . . # . .
        `)
    basic.pause(500)
}
input.onLightConditionChanged(LightCondition.Dark, function () {
    fanee()
})
```

## Étape 11 — Capteur de lumière : lumineux → fleur

☀️ La fleur s'épanouit à la lumière !

➡️ Glisse le bloc ``||input:lorsque (lumineux)||`` dans l'espace de travail.

➡️ À l'intérieur, appelle `fleur`.

> 💡 Couvre le micro:bit avec ta main pour créer de l'ombre — la fleur se fane ! Découvre-le — elle refleurit ! C'est le même composant LEDs qui affiche et qui mesure la lumière.

```blocks
function fleur() {
    basic.showLeds(`
        . # . # .
        # # # # #
        . # # # .
        . . # . .
        . . # . .
        `)
    basic.pause(500)
}
function fanee() {
    basic.showLeds(`
        . # # . .
        # . # . .
        . . # . .
        . . # . .
        . . # . .
        `)
    basic.pause(500)
}
input.onLightConditionChanged(LightCondition.Dark, function () {
    fanee()
})
input.onLightConditionChanged(LightCondition.Bright, function () {
    fleur()
})
```

## Étape 12 — Afficher la graine au démarrage

✨ La scène de départ !

➡️ Glisse le bloc ``||fonctions:appeler graine||`` à l'intérieur du bloc ``||basic:au démarrage||``.

> 💡 Dès l'allumage, la graine apparaît — prête à pousser vers la lumière !

```blocks
function graine() {
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . # . .
        . # # # .
        `)
    basic.pause(500)
}
graine()
```

## Étape 13 — Vérifier sur le simulateur

🖥️ Teste toute la fleur !

➡️ Vérifie que la graine s'affiche bien au démarrage.

➡️ Appuie sur **A** — le cycle de vie complet. Sur **B** — la fleur se fane. Sur **A+B** — floraison directe !

➡️ Clique sur l'ampoule 💡 du simulateur pour simuler l'obscurité — est-ce que la fleur se fane ? Rallume-la et observe !

> ❓ Est-ce que les transitions entre les états sont fluides ? Ajuste les pauses si besoin.

## Étape 14 — Télécharger et tester

💾 Envoie ton programme sur le micro:bit !

➡️ Clique sur le bouton **Télécharger** pour transférer ton programme.

➡️ Approche ta main au-dessus du micro:bit pour créer de l'ombre — la fleur se fane ! Éloigne-la — elle refleurit !

## Étape 15 — Question réflexive 🤔

❓ **Le capteur de lumière du micro:bit n'est pas une vraie pièce séparée — comment fonctionne-t-il selon toi ?**

❓ **Si tu voulais que la fleur passe par le bourgeon avant d'éclore quand la lumière revient, que changerais-tu dans le bloc ``||input:lorsque (lumineux)||`` ?**

> 💡 Le micro:bit utilise ses LEDs comme **capteur** en les faisant alterner rapidement entre affichage et lecture. C'est le même composant qui joue deux rôles — un exemple brillant de réutilisation !

## Étape 16 — Défi de base 🧠

➡️ Crée une fonction `eclore` qui appelle `bourgeon`, puis `fleur`.

➡️ Utilise-la à la place de `fleur` dans le bloc ``||input:lorsque (lumineux)||`` — la fleur passe maintenant par le bourgeon avant d'éclore !

> ❓ La transition est-elle plus naturelle qu'un passage direct à la floraison ?

## Étape 17 — Défi avancé 🧠

➡️ Remets le bloc ``||basic:toujours||`` dans ton programme.

➡️ À l'intérieur, place un bloc ``||logic:si/sinon||`` qui lit ``||input:niveau de lumière||`` :
- Si la lumière est **supérieure à 150** → appelle `fleur`
- Sinon si la lumière est **supérieure à 75** → appelle `bourgeon`
- Sinon → appelle `fanee`

➡️ Ajoute une ``||basic:pause (ms) 500||`` à la fin de la boucle.

```blocks
function bourgeon() {
    basic.showLeds(`
        . . # . .
        . # # # .
        . . # . .
        . . # . .
        . . # . .
        `)
    basic.pause(500)
}
function fleur() {
    basic.showLeds(`
        . # . # .
        # # # # #
        . # # # .
        . . # . .
        . . # . .
        `)
    basic.pause(500)
}
function fanee() {
    basic.showLeds(`
        . # # . .
        # . # . .
        . . # . .
        . . # . .
        . . # . .
        `)
    basic.pause(500)
}
basic.forever(function () {
    if (input.lightLevel() > 150) {
        fleur()
    } else if (input.lightLevel() > 75) {
        bourgeon()
    } else {
        fanee()
    }
    basic.pause(500)
})
```

> ❓ Couvre progressivement le micro:bit — est-ce que la fleur passe bien par le bourgeon avant de faner complètement ?

🚀 Bravo ! Tu as créé une fleur vivante qui réagit à son environnement — comme une vraie plante qui cherche la lumière !
