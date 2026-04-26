# Tutoriel 17 — Le bateau dans la tempête ⛵

## @showdialog

🎯 **Objectif** : anime un bateau qui navigue, affronte la tempête… et risque le naufrage !

Dans ce tutoriel, tu vas créer plusieurs **fonctions** — chacune représente un moment de la vie du bateau — et tu les combineras pour raconter une histoire lumineuse !

C'est parti ! 🚀

## Étape 1 — Préparer l'espace de travail

🧹 Fais le ménage !

➡️ Supprime le bloc ``||basic:toujours||``.

> 💡 On garde le bloc ``||basic:au démarrage||`` — il affichera le bateau au repos dès l'allumage !

## Étape 2 — La fonction `repos`

✨ Le bateau sur une mer calme !

➡️ Crée une fonction et nomme-la `repos`.

➡️ Glisse un bloc ``||basic:montrer LEDs||`` à l'intérieur et reproduis le dessin ci-dessous — le bateau droit avec son mât, sa voile et les petites vagues.

➡️ Ajoute un bloc ``||basic:pause (ms) 100||`` en dessous et remplace la valeur par `500`.

```blocks
function repos() {
    basic.showLeds(`
        . . # . .
        . # # # .
        # # # # #
        . . . . .
        . # . # .
        `)
    basic.pause(500)
}
```

## Étape 3 — La fonction `vague`

✨ Le bateau monte sur une vague !

➡️ Crée une fonction et nomme-la `vague`.

➡️ Le bateau est **penché à droite** — la vague le soulève par la gauche. Reproduis le dessin et ajoute une pause de `400` ms.

> 💡 Le bateau est incliné et l'eau monte à gauche — on sent le mouvement de la houle !

```blocks
function vague() {
    basic.showLeds(`
        . . . # .
        . . # # #
        . # # # #
        # . . . .
        # # . . .
        `)
    basic.pause(400)
}
```

## Étape 4 — La fonction `creux`

✨ Le bateau dans le creux de la vague !

➡️ Crée une fonction et nomme-la `creux`.

➡️ Le bateau est **au fond du creux** — l'eau monte des deux côtés. Reproduis le dessin et ajoute une pause de `400` ms.

> 💡 Les murs d'eau de chaque côté donnent l'impression que le bateau est avalé par la mer !

```blocks
function creux() {
    basic.showLeds(`
        . . # . .
        . # # # .
        # # # # #
        # . . . #
        # . . . #
        `)
    basic.pause(400)
}
```

## Étape 5 — La fonction `navigation`

✨ Une fonction qui raconte une histoire !

➡️ Crée une fonction et nomme-la `navigation`.

➡️ À l'intérieur, appelle successivement : `repos`, `vague`, `creux`, `vague`, `repos`.

> 💡 `navigation` ne dessine rien elle-même — elle **orchestre** les autres fonctions pour raconter le trajet complet d'une vague ! C'est une fonction qui appelle d'autres fonctions.

```blocks
function navigation() {
    repos()
    vague()
    creux()
    vague()
    repos()
}
```

## Étape 6 — La fonction `eclair`

⚡ La tempête approche !

➡️ Crée une fonction et nomme-la `eclair`.

➡️ Glisse un bloc ``||basic:montrer LEDs||`` et reproduis un éclair qui fend le ciel du haut vers le bas.

➡️ Ajoute une pause de `150` ms, puis ``||basic:effacer l'écran||``, puis une autre pause de `150` ms.

> 💡 L'écran s'allume brusquement puis s'éteint — l'effet de l'éclair est dans ce contraste rapide entre lumière et noir !

```blocks
function eclair() {
    basic.showLeds(`
        # # . # #
        . # . # .
        . # # # .
        . . # . .
        . . # . .
        `)
    basic.pause(150)
    basic.clearScreen()
    basic.pause(150)
}
```

## Étape 7 — La fonction `tempete`

🌊 La tempête en pleine force !

➡️ Crée une fonction et nomme-la `tempete`.

➡️ Glisse un bloc ``||loops:répéter 3 fois||`` à l'intérieur.

➡️ Dans la boucle, appelle `eclair` puis `navigation`.

> 💡 La tempête, c'est trois cycles de : éclair → bateau secoué par une vague. Trois lignes de code, mais une vraie histoire lumineuse !

```blocks
function tempete() {
    for (let index = 0; index < 3; index++) {
        eclair()
        navigation()
    }
}
```

## Étape 8 — La fonction `naufrage`

💀 Le pire des scénarios !

➡️ Crée une fonction et nomme-la `naufrage`.

➡️ Glisse **quatre** blocs ``||basic:montrer LEDs||`` à la suite, chacun suivi d'une pause de `400` ms, puis ``||basic:effacer l'écran||`` à la fin.

➡️ Reproduis les quatre images ci-dessous dans l'ordre — le bateau coule progressivement.

> 💡 Chaque image fait descendre le bateau d'un cran — l'animation donne l'illusion que l'eau monte et engloutit le bateau !

```blocks
function naufrage() {
    basic.showLeds(`
        . . # . .
        . # # # .
        # # # # #
        # # # # #
        # # # # #
        `)
    basic.pause(400)
    basic.showLeds(`
        . . . . .
        . . # . .
        # # # # #
        # # # # #
        # # # # #
        `)
    basic.pause(400)
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        # # # # #
        # # # # #
        `)
    basic.pause(400)
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        # # # # #
        `)
    basic.pause(600)
    basic.clearScreen()
}
```

## Étape 9 — Bouton A : navigation

➡️ Glisse le bloc ``||input:lorsque le bouton A est pressé||`` dans l'espace de travail.

➡️ À l'intérieur, appelle `navigation`.

```blocks
input.onButtonPressed(Button.A, function () {
    navigation()
})
```

## Étape 10 — Bouton B : eclair

➡️ Glisse le bloc ``||input:lorsque le bouton B est pressé||`` dans l'espace de travail.

➡️ À l'intérieur, appelle `eclair`.

```blocks
input.onButtonPressed(Button.B, function () {
    eclair()
})
```

## Étape 11 — Bouton A+B : tempete

➡️ Glisse le bloc ``||input:lorsque le bouton A+B est pressé||`` dans l'espace de travail.

➡️ À l'intérieur, appelle `tempete`.

```blocks
input.onButtonPressed(Button.AB, function () {
    tempete()
})
```

## Étape 12 — Secousse : naufrage

➡️ Glisse le bloc ``||input:lorsque secouer||`` dans l'espace de travail.

➡️ À l'intérieur, appelle `naufrage`.

> 💡 Secouer le micro:bit simule une tempête trop violente — le bateau coule ! C'est le moment dramatique de ton histoire !

```blocks
input.onGesture(Gesture.Shake, function () {
    naufrage()
})
```

## Étape 13 — Afficher le bateau au démarrage

✨ La scène de départ !

➡️ Glisse le bloc ``||fonctions:appeler repos||`` à l'intérieur du bloc ``||basic:au démarrage||``.

> 💡 Dès l'allumage, le bateau apparaît sereinement sur une mer calme — avant que la tempête éclate !

```blocks
basic.showLeds(`
    . . # . .
    . # # # .
    # # # # #
    . . . . .
    . # . # .
    `)
```

## Étape 14 — Vérifier sur le simulateur

🖥️ Teste toute l'histoire !

➡️ Vérifie que le bateau s'affiche bien au démarrage.

➡️ Appuie sur **A** — le bateau navigue. Sur **B** — l'éclair. Sur **A+B** — la tempête complète.

➡️ Clique sur **SHAKE** — le naufrage !

> ❓ Est-ce que l'animation du naufrage donne bien l'impression que le bateau coule ? Ajuste les pauses si besoin.

## Étape 15 — Télécharger et tester

💾 Envoie ton programme sur le micro:bit !

➡️ Clique sur le bouton **Télécharger** pour transférer ton programme.

➡️ Raconte l'histoire : mer calme → navigation → tempête → naufrage !

## Étape 16 — Question réflexive 🤔

❓ **La fonction `navigation` ne contient aucun bloc ``||basic:montrer LEDs||`` — pourtant elle affiche cinq images. Comment est-ce possible ?**

❓ **Si tu voulais que la tempête dure plus longtemps, quelle est la seule valeur à changer dans ton programme ?**

> 💡 `navigation` **délègue** l'affichage à `repos`, `vague` et `creux` — elle n'a pas besoin de savoir comment dessiner, elle sait seulement **dans quel ordre appeler**. C'est le principe de la **composition** : des petites fonctions simples s'assemblent pour créer quelque chose de complexe !

## Étape 17 — Défi de base 🧠

➡️ Ajoute une fonction `arc_en_ciel` qui affiche une ligne de LEDs qui se remplit rangée par rangée de haut en bas, pour simuler une éclaircie après la tempête.

➡️ Appelle-la à la fin de la fonction `tempete`.

> ❓ Est-ce que l'éclaircie arrive bien après la dernière vague de la tempête ?

## Étape 18 — Défi avancé 🧠

➡️ Crée une fonction `histoire` qui raconte tout : `navigation`, `tempete`, `naufrage`.

➡️ Ajoute une icône ``||basic:montrer l'icône||`` ☠️ à la fin de `naufrage` pour marquer la fin de l'histoire.

➡️ Déclenche `histoire` avec une inclinaison à gauche ``||input:lorsque incliné à gauche||``.

```blocks
function histoire() {
    navigation()
    tempete()
    naufrage()
}
input.onGesture(Gesture.TiltLeft, function () {
    histoire()
})
```

> ❓ Combien de dessins différents s'affichent en tout pendant `histoire` ? Compte-les !

🚀 Bravo ! Tu as programmé une vraie histoire animée — le bateau navigue, la tempête éclate, et le sort du marin est entre tes mains… ou plutôt entre tes boutons !
