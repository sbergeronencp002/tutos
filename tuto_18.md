# Tutoriel 18 — La chauve-souris 🦇

## @showdialog

🎯 **Objectif** : anime une chauve-souris qui vole grâce aux **fonctions** !

Dans ce tutoriel, tu vas créer trois positions d'ailes, les combiner pour simuler un vrai battement, et même faire plonger ta chauve-souris hors de l'écran !

C'est parti ! 🚀

## Étape 1 — Préparer l'espace de travail

🧹 Fais le ménage !

➡️ Supprime le bloc ``||basic:toujours||``.

> 💡 On garde le bloc ``||basic:au démarrage||`` — il affichera la chauve-souris au repos dès l'allumage !

## Étape 2 — La fonction `ailesHaut`

✨ Première position des ailes !

➡️ Crée une fonction et nomme-la `ailesHaut`.

➡️ Glisse un bloc ``||basic:montrer LEDs||`` à l'intérieur — les ailes sont **levées**, les pointes en haut des coins.

➡️ Ajoute un bloc ``||basic:pause (ms) 100||`` en dessous et remplace la valeur par `300`.

```blocks
function ailesHaut() {
    basic.showLeds(`
        # . # . #
        # # # # #
        . . # . .
        . # . # .
        . . . . .
        `)
    basic.pause(300)
}
```

## Étape 3 — La fonction `ailesMilieu`

✨ Position neutre — la chauve-souris plane !

➡️ Crée une fonction et nomme-la `ailesMilieu`.

➡️ Les ailes sont **horizontales**, le corps bien visible au centre.

➡️ Ajoute une pause de `300` ms.

```blocks
function ailesMilieu() {
    basic.showLeds(`
        . . . . .
        # # # # #
        . # # # .
        . . # . .
        . . . . .
        `)
    basic.pause(300)
}
```

## Étape 4 — La fonction `ailesBas`

✨ Troisième position — les ailes poussent vers le bas !

➡️ Crée une fonction et nomme-la `ailesBas`.

➡️ Les ailes sont **baissées**, les pointes en bas des coins.

➡️ Ajoute une pause de `300` ms.

```blocks
function ailesBas() {
    basic.showLeds(`
        . . . . .
        . # . # .
        . . # . .
        # # # # #
        # . # . #
        `)
    basic.pause(300)
}
```

## Étape 5 — La fonction `vol`

✨ Un vrai battement d'ailes !

➡️ Crée une fonction et nomme-la `vol`.

➡️ À l'intérieur, appelle successivement : `ailesMilieu`, `ailesHaut`, `ailesMilieu`, `ailesBas`, `ailesMilieu`.

> 💡 `vol` ne dessine rien elle-même — elle **orchestre** les trois positions pour simuler un battement d'ailes complet, du repos en haut jusqu'au repos en bas !

```blocks
function ailesHaut() {
    basic.showLeds(`
        # . # . #
        # # # # #
        . . # . .
        . # . # .
        . . . . .
        `)
    basic.pause(300)
}
function ailesMilieu() {
    basic.showLeds(`
        . . . . .
        # # # # #
        . # # # .
        . . # . .
        . . . . .
        `)
    basic.pause(300)
}
function ailesBas() {
    basic.showLeds(`
        . . . . .
        . # . # .
        . . # . .
        # # # # #
        # . # . #
        `)
    basic.pause(300)
}
function vol() {
    ailesMilieu()
    ailesHaut()
    ailesMilieu()
    ailesBas()
    ailesMilieu()
}
```

## Étape 6 — La fonction `chasse`

🦇 La chauve-souris chasse un insecte — elle bat des ailes rapidement !

➡️ Crée une fonction et nomme-la `chasse`.

➡️ Glisse un bloc ``||loops:répéter 5 fois||`` à l'intérieur.

➡️ Dans la boucle, appelle `ailesHaut` puis `ailesBas`.

➡️ Après la boucle, appelle `ailesMilieu` pour revenir au repos.

> 💡 En appelant `ailesHaut` et `ailesBas` directement sans passer par `ailesMilieu`, le battement est **deux fois plus rapide** — comme une chauve-souris en plein sprint !

```blocks
function ailesHaut() {
    basic.showLeds(`
        # . # . #
        # # # # #
        . . # . .
        . # . # .
        . . . . .
        `)
    basic.pause(300)
}
function ailesMilieu() {
    basic.showLeds(`
        . . . . .
        # # # # #
        . # # # .
        . . # . .
        . . . . .
        `)
    basic.pause(300)
}
function ailesBas() {
    basic.showLeds(`
        . . . . .
        . # . # .
        . . # . .
        # # # # #
        # . # . #
        `)
    basic.pause(300)
}
function chasse() {
    for (let index = 0; index < 5; index++) {
        ailesHaut()
        ailesBas()
    }
    ailesMilieu()
}
```

## Étape 7 — La fonction `plonger`

🌑 La chauve-souris plonge dans l'obscurité !

➡️ Crée une fonction et nomme-la `plonger`.

➡️ Glisse **quatre** blocs ``||basic:montrer LEDs||`` à la suite, chacun suivi d'une pause de `300` ms, puis ``||basic:effacer l'écran||`` à la fin.

➡️ Reproduis les quatre images ci-dessous dans l'ordre — la chauve-souris descend rangée par rangée jusqu'à disparaître.

> 💡 Chaque image décale la chauve-souris d'une rangée vers le bas — elle glisse hors de l'écran comme si elle plongeait dans la nuit !

```blocks
function plonger() {
    basic.showLeds(`
        . . . . .
        # . # . #
        # # # # #
        . . # . .
        . # . # .
        `)
    basic.pause(300)
    basic.showLeds(`
        . . . . .
        . . . . .
        # . # . #
        # # # # #
        . . # . .
        `)
    basic.pause(300)
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        # . # . #
        # # # # #
        `)
    basic.pause(300)
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        # . # . #
        `)
    basic.pause(300)
    basic.clearScreen()
}
```

## Étape 8 — Bouton A : vol

➡️ Glisse le bloc ``||input:lorsque le bouton A est pressé||`` dans l'espace de travail.

➡️ À l'intérieur, appelle `vol`.

```blocks
function ailesHaut() {
    basic.showLeds(`
        # . # . #
        # # # # #
        . . # . .
        . # . # .
        . . . . .
        `)
    basic.pause(300)
}
function ailesMilieu() {
    basic.showLeds(`
        . . . . .
        # # # # #
        . # # # .
        . . # . .
        . . . . .
        `)
    basic.pause(300)
}
function ailesBas() {
    basic.showLeds(`
        . . . . .
        . # . # .
        . . # . .
        # # # # #
        # . # . #
        `)
    basic.pause(300)
}
function vol() {
    ailesMilieu()
    ailesHaut()
    ailesMilieu()
    ailesBas()
    ailesMilieu()
}
input.onButtonPressed(Button.A, function () {
    vol()
})
```

## Étape 9 — Bouton B : plonger

➡️ Glisse le bloc ``||input:lorsque le bouton B est pressé||`` dans l'espace de travail.

➡️ À l'intérieur, appelle `plonger`.

```blocks
function plonger() {
    basic.showLeds(`
        . . . . .
        # . # . #
        # # # # #
        . . # . .
        . # . # .
        `)
    basic.pause(300)
    basic.showLeds(`
        . . . . .
        . . . . .
        # . # . #
        # # # # #
        . . # . .
        `)
    basic.pause(300)
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        # . # . #
        # # # # #
        `)
    basic.pause(300)
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        # . # . #
        `)
    basic.pause(300)
    basic.clearScreen()
}
input.onButtonPressed(Button.B, function () {
    plonger()
})
```

## Étape 10 — Bouton A+B : chasse

➡️ Glisse le bloc ``||input:lorsque le bouton A+B est pressé||`` dans l'espace de travail.

➡️ À l'intérieur, appelle `chasse`.

```blocks
function ailesHaut() {
    basic.showLeds(`
        # . # . #
        # # # # #
        . . # . .
        . # . # .
        . . . . .
        `)
    basic.pause(300)
}
function ailesMilieu() {
    basic.showLeds(`
        . . . . .
        # # # # #
        . # # # .
        . . # . .
        . . . . .
        `)
    basic.pause(300)
}
function ailesBas() {
    basic.showLeds(`
        . . . . .
        . # . # .
        . . # . .
        # # # # #
        # . # . #
        `)
    basic.pause(300)
}
function vol() {
    ailesMilieu()
    ailesHaut()
    ailesMilieu()
    ailesBas()
    ailesMilieu()
}
function plonger() {
    basic.showLeds(`
        . . . . .
        # . # . #
        # # # # #
        . . # . .
        . # . # .
        `)
    basic.pause(300)
    basic.showLeds(`
        . . . . .
        . . . . .
        # . # . #
        # # # # #
        . . # . .
        `)
    basic.pause(300)
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        # . # . #
        # # # # #
        `)
    basic.pause(300)
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        # . # . #
        `)
    basic.pause(300)
    basic.clearScreen()
}
function chasse() {
    for (let index = 0; index < 5; index++) {
        ailesHaut()
        ailesBas()
    }
    ailesMilieu()
}
input.onButtonPressed(Button.A, function () {
    vol()
})
input.onButtonPressed(Button.B, function () {
    plonger()
})
input.onButtonPressed(Button.AB, function () {
    chasse()
})
```

## Étape 11 — Afficher la chauve-souris au démarrage

✨ La scène de départ !

➡️ Glisse le bloc ``||fonctions:appeler ailesMilieu||`` à l'intérieur du bloc ``||basic:au démarrage||``.

> 💡 Dès l'allumage, la chauve-souris apparaît en vol plané — prête à partir chasser !

```blocks
function ailesMilieu() {
    basic.showLeds(`
        . . . . .
        # # # # #
        . # # # .
        . . # . .
        . . . . .
        `)
    basic.pause(300)
}
ailesMilieu()
```

## Étape 12 — Vérifier sur le simulateur

🖥️ Teste toute l'animation !

➡️ Vérifie que la chauve-souris s'affiche bien au démarrage.

➡️ Appuie sur **A** — un battement d'ailes complet. Sur **B** — le plongeon. Sur **A+B** — la chasse rapide !

> ❓ Est-ce que le mouvement des ailes est fluide ? Modifie la valeur des pauses dans tes fonctions pour accélérer ou ralentir.

## Étape 13 — Télécharger et tester

💾 Envoie ton programme sur le micro:bit !

➡️ Clique sur le bouton **Télécharger** pour transférer ton programme.

➡️ Appuie sur **A+B** et observe la chauve-souris partir à la chasse !

## Étape 14 — Question réflexive 🤔

❓ **La fonction `vol` appelle `ailesMilieu` trois fois. Pourquoi ne pas avoir écrit le dessin trois fois directement ?**

❓ **Si tu voulais que toutes les animations soient deux fois plus rapides, combien de valeurs devrais-tu changer dans ton programme ?**

> 💡 Avec les fonctions, modifier la pause dans `ailesMilieu` **une seule fois** change la vitesse partout où elle est appelée — dans `vol` ET dans `chasse`. Sans fonctions, il faudrait retrouver et modifier chaque bloc individuellement. C'est ça, la puissance de la **réutilisabilité** !

## Étape 15 — Défi de base 🧠

➡️ Crée une fonction `nuit` qui appelle `vol` trois fois de suite, suivie de `plonger`.

➡️ Déclenche `nuit` avec une secousse ``||input:lorsque secouer||``.

> ❓ Est-ce que la chauve-souris bat des ailes trois fois avant de disparaître dans la nuit ?

## Étape 16 — Défi avancé 🧠

➡️ Ajoute une fonction `surgir` — l'animation inverse de `plonger` : la chauve-souris **monte** dans l'écran depuis le bas, rangée par rangée.

➡️ Appelle `surgir` avec une inclinaison ``||input:lorsque incliné à gauche||``, puis `plonger` avec une inclinaison ``||input:lorsque incliné à droite||``.

```blocks
function ailesMilieu() {
    basic.showLeds(`
        . . . . .
        # # # # #
        . # # # .
        . . # . .
        . . . . .
        `)
    basic.pause(300)
}
function plonger() {
    basic.showLeds(`
        . . . . .
        # . # . #
        # # # # #
        . . # . .
        . # . # .
        `)
    basic.pause(300)
    basic.showLeds(`
        . . . . .
        . . . . .
        # . # . #
        # # # # #
        . . # . .
        `)
    basic.pause(300)
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        # . # . #
        # # # # #
        `)
    basic.pause(300)
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        # . # . #
        `)
    basic.pause(300)
    basic.clearScreen()
}
function surgir() {
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        # . # . #
        `)
    basic.pause(300)
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        # . # . #
        # # # # #
        `)
    basic.pause(300)
    basic.showLeds(`
        . . . . .
        . . . . .
        # . # . #
        # # # # #
        . . # . .
        `)
    basic.pause(300)
    basic.showLeds(`
        . . . . .
        # . # . #
        # # # # #
        . . # . .
        . # . # .
        `)
    basic.pause(300)
    ailesMilieu()
}
input.onGesture(Gesture.TiltLeft, function () {
    surgir()
})
input.onGesture(Gesture.TiltRight, function () {
    plonger()
})
```

> ❓ Est-ce que la chauve-souris surgit bien de l'obscurité et disparaît dans la nuit quand tu inclines le micro:bit ?

🚀 Bravo ! Tu as animé une vraie chauve-souris — elle vole, chasse et plonge dans la nuit grâce à tes fonctions !
