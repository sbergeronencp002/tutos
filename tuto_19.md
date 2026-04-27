# Tutoriel 19 — La fusée 🚀

## @showdialog

🎯 **Objectif** : anime une fusée qui décolle, part en orbite et rentre sur Terre grâce aux **fonctions** !

Dans ce tutoriel, tu vas créer quatre fonctions — chacune représente une étape du voyage spatial — et tu les combineras pour raconter une vraie mission !

C'est parti ! 🚀

## Étape 1 — Préparer l'espace de travail

🧹 Fais le ménage !

➡️ Supprime le bloc ``||basic:toujours||``.

> 💡 On garde le bloc ``||basic:au démarrage||`` — il affichera la fusée sur son pas de tir dès l'allumage !

## Étape 2 — La fonction `attente`

✨ La fusée sur son pas de tir !

➡️ Crée une fonction et nomme-la `attente`.

➡️ Glisse un bloc ``||basic:montrer LEDs||`` à l'intérieur — la fusée est dressée, nez pointu en haut, supports au sol.

➡️ Ajoute un bloc ``||basic:pause (ms) 100||`` en dessous et remplace la valeur par `500`.

```blocks
function attente() {
    basic.showLeds(`
        . . # . .
        . # # # .
        . # # # .
        # # # # #
        # . . . #
        `)
    basic.pause(500)
}
```

## Étape 3 — La fonction `decollage`

🔥 Allumage des moteurs !

➡️ Crée une fonction et nomme-la `decollage`.

➡️ Les supports sont remplacés par les flammes — reproduis le dessin et ajoute une pause de `400` ms.

> 💡 Le bas de la grille change : les supports rigides laissent place aux flammes des moteurs — la fusée s'arrache du sol !

```blocks
function decollage() {
    basic.showLeds(`
        . . # . .
        . # # # .
        . # # # .
        # # # # #
        . # # # .
        `)
    basic.pause(400)
}
```

## Étape 4 — La fonction `orbite`

🌟 La fusée dans l'espace !

➡️ Crée une fonction et nomme-la `orbite`.

➡️ Des étoiles apparaissent aux coins — la fusée flotte, sans sol sous elle. Reproduis le dessin et ajoute une pause de `500` ms.

> 💡 Les quatre étoiles aux coins indiquent que la fusée est dans l'espace — plus de pas de tir, plus de flammes !

```blocks
function orbite() {
    basic.showLeds(`
        # . . . #
        . . # . .
        . # # # .
        # # # # #
        # . . . #
        `)
    basic.pause(500)
}
```

## Étape 5 — La fonction `rentre`

🌡️ Rentrée dans l'atmosphère !

➡️ Crée une fonction et nomme-la `rentre`.

➡️ La fusée est **retournée** — le bouclier thermique (la partie large) affronte la chaleur en premier. Reproduis le dessin et ajoute une pause de `400` ms.

> 💡 C'est le même dessin qu'`attente`, mais à l'envers ! Dans la vraie vie, les capsules rentrent sur Terre avec leur base en avant pour résister à la chaleur de la rentrée atmosphérique.

```blocks
function rentre() {
    basic.showLeds(`
        # # # # #
        . # # # .
        . # # # .
        . # # # .
        . . # . .
        `)
    basic.pause(400)
}
```

## Étape 6 — La fonction `mission`

✨ Un voyage complet !

➡️ Crée une fonction et nomme-la `mission`.

➡️ À l'intérieur, appelle successivement : `attente`, `decollage`, `orbite`, `rentre`.

> 💡 `mission` ne dessine rien elle-même — elle **orchestre** les quatre étapes du voyage spatial ! C'est une fonction qui appelle d'autres fonctions.

```blocks
function attente() {
    basic.showLeds(`
        . . # . .
        . # # # .
        . # # # .
        # # # # #
        # . . . #
        `)
    basic.pause(500)
}
function decollage() {
    basic.showLeds(`
        . . # . .
        . # # # .
        . # # # .
        # # # # #
        . # # # .
        `)
    basic.pause(400)
}
function orbite() {
    basic.showLeds(`
        # . . . #
        . . # . .
        . # # # .
        # # # # #
        # . . . #
        `)
    basic.pause(500)
}
function rentre() {
    basic.showLeds(`
        # # # # #
        . # # # .
        . # # # .
        . # # # .
        . . # . .
        `)
    basic.pause(400)
}
function mission() {
    attente()
    decollage()
    orbite()
    rentre()
}
```

## Étape 7 — La fonction `atterrissage`

🪂 La fusée descend vers le sol !

➡️ Crée une fonction et nomme-la `atterrissage`.

➡️ Glisse **quatre** blocs ``||basic:montrer LEDs||`` à la suite, chacun suivi d'une pause de `300` ms, puis ``||basic:effacer l'écran||`` à la fin.

➡️ Reproduis les quatre images ci-dessous dans l'ordre — la fusée descend rangée par rangée jusqu'à disparaître.

> 💡 Chaque image décale la fusée d'une rangée vers le bas — elle glisse hors de l'écran comme si elle atterrissait !

```blocks
function atterrissage() {
    basic.showLeds(`
        . . # . .
        . # # # .
        # # # # #
        . . . . .
        . . . . .
        `)
    basic.pause(300)
    basic.showLeds(`
        . . . . .
        . . # . .
        . # # # .
        # # # # #
        . . . . .
        `)
    basic.pause(300)
    basic.showLeds(`
        . . . . .
        . . . . .
        . . # . .
        . # # # .
        # # # # #
        `)
    basic.pause(300)
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . # . .
        . # # # .
        `)
    basic.pause(300)
    basic.clearScreen()
}
```

## Étape 8 — Bouton A : decollage

➡️ Glisse le bloc ``||input:lorsque le bouton A est pressé||`` dans l'espace de travail.

➡️ À l'intérieur, appelle `decollage`.

```blocks
function decollage() {
    basic.showLeds(`
        . . # . .
        . # # # .
        . # # # .
        # # # # #
        . # # # .
        `)
    basic.pause(400)
}
input.onButtonPressed(Button.A, function () {
    decollage()
})
```

## Étape 9 — Bouton B : orbite

➡️ Glisse le bloc ``||input:lorsque le bouton B est pressé||`` dans l'espace de travail.

➡️ À l'intérieur, appelle `orbite`.

```blocks
function orbite() {
    basic.showLeds(`
        # . . . #
        . . # . .
        . # # # .
        # # # # #
        # . . . #
        `)
    basic.pause(500)
}
input.onButtonPressed(Button.B, function () {
    orbite()
})
```

## Étape 10 — Bouton A+B : mission

➡️ Glisse le bloc ``||input:lorsque le bouton A+B est pressé||`` dans l'espace de travail.

➡️ À l'intérieur, appelle `mission`.

```blocks
function attente() {
    basic.showLeds(`
        . . # . .
        . # # # .
        . # # # .
        # # # # #
        # . . . #
        `)
    basic.pause(500)
}
function decollage() {
    basic.showLeds(`
        . . # . .
        . # # # .
        . # # # .
        # # # # #
        . # # # .
        `)
    basic.pause(400)
}
function orbite() {
    basic.showLeds(`
        # . . . #
        . . # . .
        . # # # .
        # # # # #
        # . . . #
        `)
    basic.pause(500)
}
function rentre() {
    basic.showLeds(`
        # # # # #
        . # # # .
        . # # # .
        . # # # .
        . . # . .
        `)
    basic.pause(400)
}
function mission() {
    attente()
    decollage()
    orbite()
    rentre()
}
input.onButtonPressed(Button.A, function () {
    decollage()
})
input.onButtonPressed(Button.B, function () {
    orbite()
})
input.onButtonPressed(Button.AB, function () {
    mission()
})
```

## Étape 11 — Secousse : atterrissage

➡️ Glisse le bloc ``||input:lorsque secouer||`` dans l'espace de travail.

➡️ À l'intérieur, appelle `atterrissage`.

> 💡 Secouer le micro:bit simule les turbulences de la rentrée atmosphérique — la fusée amorce son atterrissage !

```blocks
function atterrissage() {
    basic.showLeds(`
        . . # . .
        . # # # .
        # # # # #
        . . . . .
        . . . . .
        `)
    basic.pause(300)
    basic.showLeds(`
        . . . . .
        . . # . .
        . # # # .
        # # # # #
        . . . . .
        `)
    basic.pause(300)
    basic.showLeds(`
        . . . . .
        . . . . .
        . . # . .
        . # # # .
        # # # # #
        `)
    basic.pause(300)
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . # . .
        . # # # .
        `)
    basic.pause(300)
    basic.clearScreen()
}
input.onGesture(Gesture.Shake, function () {
    atterrissage()
})
```

## Étape 12 — Afficher la fusée au démarrage

✨ La scène de départ !

➡️ Glisse le bloc ``||fonctions:appeler attente||`` à l'intérieur du bloc ``||basic:au démarrage||``.

> 💡 Dès l'allumage, la fusée apparaît sur son pas de tir — prête à décoller !

```blocks
function attente() {
    basic.showLeds(`
        . . # . .
        . # # # .
        . # # # .
        # # # # #
        # . . . #
        `)
    basic.pause(500)
}
attente()
```

## Étape 13 — Vérifier sur le simulateur

🖥️ Teste toute la mission !

➡️ Vérifie que la fusée s'affiche bien au démarrage sur son pas de tir.

➡️ Appuie sur **A** — les moteurs s'allument. Sur **B** — la vue depuis l'espace. Sur **A+B** — la mission complète !

➡️ Clique sur **SHAKE** — l'atterrissage !

> ❓ Est-ce que l'animation de l'atterrissage donne bien l'impression que la fusée descend ? Ajuste les pauses si besoin.

## Étape 14 — Télécharger et tester

💾 Envoie ton programme sur le micro:bit !

➡️ Clique sur le bouton **Télécharger** pour transférer ton programme.

➡️ Lance la mission : pas de tir → décollage → orbite → rentrée → atterrissage !

## Étape 15 — Question réflexive 🤔

❓ **La fonction `rentre` montre la même fusée qu'`attente`, mais à l'envers. Que représente ce retournement dans la vraie vie ?**

❓ **Si tu voulais que la fusée reste plus longtemps en orbite, quelle est la seule valeur à modifier dans ton programme ?**

> 💡 `mission` **délègue** chaque étape à une fonction spécialisée — elle sait dans quel ordre appeler, mais pas comment dessiner. C'est le principe de la **composition** : de petites fonctions simples s'assemblent pour raconter une grande histoire !

## Étape 16 — Défi de base 🧠

➡️ Crée une fonction `vol_orbital` qui appelle `orbite` trois fois de suite — la fusée fait trois tours de la Terre !

➡️ Déclenche `vol_orbital` avec une inclinaison ``||input:lorsque incliné à gauche||``.

> ❓ Est-ce que la fusée reste bien dans l'espace pendant les trois tours ?

## Étape 17 — Défi avancé 🧠

➡️ Crée une fonction `lancement` — l'animation inverse de `atterrissage` : la fusée **monte** depuis le bas de l'écran, rangée par rangée, jusqu'à disparaître vers le haut.

➡️ Déclenche `lancement` avec une inclinaison ``||input:lorsque incliné à droite||``.

```blocks
function attente() {
    basic.showLeds(`
        . . # . .
        . # # # .
        . # # # .
        # # # # #
        # . . . #
        `)
    basic.pause(500)
}
function lancement() {
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . # . .
        . # # # .
        `)
    basic.pause(300)
    basic.showLeds(`
        . . . . .
        . . . . .
        . . # . .
        . # # # .
        # # # # #
        `)
    basic.pause(300)
    basic.showLeds(`
        . . . . .
        . . # . .
        . # # # .
        # # # # #
        . . . . .
        `)
    basic.pause(300)
    basic.showLeds(`
        . . # . .
        . # # # .
        # # # # #
        . . . . .
        . . . . .
        `)
    basic.pause(300)
    attente()
}
input.onGesture(Gesture.TiltRight, function () {
    lancement()
})
```

> ❓ Est-ce que la fusée monte bien depuis le bas de l'écran ? Compare avec `atterrissage` — c'est exactement l'inverse !

🚀 Bravo ! Tu as programmé une vraie mission spatiale — décollage, orbite, rentrée et atterrissage grâce à tes fonctions !
