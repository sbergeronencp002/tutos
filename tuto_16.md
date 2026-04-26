# Tutoriel 16 — Le jumping jack 🤸

## @showdialog

🎯 **Objectif** : anime un personnage qui fait des jumping jacks grâce aux **fonctions** !

Dans ce tutoriel, tu vas découvrir les blocs **Fonctions** — ils te permettent de donner un nom à une séquence d'actions et de l'utiliser plusieurs fois dans ton programme.

C'est parti ! 🚀

## Étape 1 — Préparer l'espace de travail

🧹 Fais le ménage !

➡️ Supprime le bloc ``||basic:toujours||``.

> 💡 On garde le bloc ``||basic:au démarrage||`` — on va s'en servir à la toute fin !

## Étape 2 — Créer la fonction `Bras`

✨ Nouvelle notion : la **fonction** !

➡️ Clique sur **Fonctions** dans le menu, puis sur **Créer une fonction**.

➡️ Nomme-la `Bras`.

> 💡 Une **fonction**, c'est comme une recette à laquelle tu donnes un nom. Tu écris les instructions une seule fois, et tu peux les utiliser autant de fois que tu veux dans ton programme !

## Étape 3 — Dessiner le personnage bras levés

✨ Remplis ta première fonction !

➡️ Glisse le bloc ``||basic:montrer LEDs||`` à l'intérieur du bloc ``||fonctions:fonction Bras||``.

➡️ Reproduis le dessin ci-dessous — le personnage avec les bras **levés** en V.

➡️ Glisse ensuite un bloc ``||basic:pause (ms) 100||`` en dessous et remplace la valeur par `400`.

```blocks
function Bras() {
    basic.showLeds(`
        # . # . #
        . # # # .
        . . # . .
        . # . # .
        # . . . #
        `)
    basic.pause(400)
}
```

## Étape 4 — Créer la fonction `Jambes`

✨ Crée ta deuxième fonction !

➡️ Clique sur **Fonctions** dans le menu, puis sur **Créer une fonction**.

➡️ Nomme-la `Jambes`.

## Étape 5 — Dessiner le personnage bras bas, jambes écartées

✨ Remplis ta deuxième fonction !

➡️ Glisse le bloc ``||basic:montrer LEDs||`` à l'intérieur du bloc ``||fonctions:fonction Jambes||``.

➡️ Reproduis le dessin ci-dessous — le personnage avec les bras **baissés** et les jambes **écartées**.

➡️ Glisse ensuite un bloc ``||basic:pause (ms) 100||`` en dessous et remplace la valeur par `400`.

```blocks
function Jambes() {
    basic.showLeds(`
        . . # . .
        # # # # #
        . . # . .
        . # . # .
        # . . . #
        `)
    basic.pause(400)
}
```

## Étape 6 — Tester chaque fonction avec un bouton

✨ Associe chaque fonction à un bouton !

➡️ Glisse le bloc ``||fonctions:appeler Bras||`` à l'intérieur du bloc ``||input:lorsque le bouton A est pressé||``.

➡️ Glisse le bloc ``||fonctions:appeler Jambes||`` à l'intérieur du bloc ``||input:lorsque le bouton B est pressé||``.

> 💡 **Appeler** une fonction, c'est lui dire : *"Exécute-toi maintenant !"* En appuyant sur **A**, tu vois les bras levés. En appuyant sur **B**, tu vois les bras bas et les jambes écartées.

```blocks
function Bras() {
    basic.showLeds(`
        # . # . #
        . # # # .
        . . # . .
        . # . # .
        # . . . #
        `)
    basic.pause(400)
}
function Jambes() {
    basic.showLeds(`
        . . # . .
        # # # # #
        . . # . .
        . # . # .
        # . . . #
        `)
    basic.pause(400)
}
input.onButtonPressed(Button.A, function () {
    Bras()
})
input.onButtonPressed(Button.B, function () {
    Jambes()
})
```

## Étape 7 — Vérifier sur le simulateur

🖥️ Observe le résultat avant de continuer !

➡️ Appuie sur **A** — est-ce que le personnage a bien les bras levés ?

➡️ Appuie sur **B** — est-ce que le personnage a bien les bras bas et les jambes écartées ?

> ❓ Retouche les cases de tes dessins si quelque chose ne va pas !

## Étape 8 — Animer le jumping jack avec le bouton A+B

✨ Assemble l'animation complète !

➡️ Glisse un bloc ``||loops:répéter 4 fois||`` à l'intérieur du bloc ``||input:lorsque le bouton A+B est pressé||``.

➡️ Remplace la valeur `4` par `6`.

➡️ À l'intérieur de la boucle, glisse successivement :
- ``||fonctions:appeler Bras||``
- ``||fonctions:appeler Jambes||``

> 💡 La boucle appelle tes deux fonctions en alternance **6 fois** — le personnage fait **6 jumping jacks** ! Tu n'as pas besoin de réécrire les dessins — les fonctions s'en chargent !

```blocks
function Bras() {
    basic.showLeds(`
        # . # . #
        . # # # .
        . . # . .
        . # . # .
        # . . . #
        `)
    basic.pause(400)
}
function Jambes() {
    basic.showLeds(`
        . . # . .
        # # # # #
        . . # . .
        . # . # .
        # . . . #
        `)
    basic.pause(400)
}
input.onButtonPressed(Button.A, function () {
    Bras()
})
input.onButtonPressed(Button.B, function () {
    Jambes()
})
input.onButtonPressed(Button.AB, function () {
    for (let index = 0; index < 6; index++) {
        Bras()
        Jambes()
    }
})
```

## Étape 9 — Afficher le personnage au repos au démarrage

✨ Ajoute une position de départ !

➡️ Glisse le bloc ``||basic:montrer LEDs||`` à l'intérieur du bloc ``||basic:au démarrage||``.

➡️ Reproduis le personnage debout, bras le long du corps et jambes jointes.

> 💡 Au démarrage, le micro:bit affiche le personnage **au repos**, avant que tu appuies sur un bouton. C'est sa position de départ !

```blocks
function Bras() {
    basic.showLeds(`
        # . # . #
        . # # # .
        . . # . .
        . # . # .
        # . . . #
        `)
    basic.pause(400)
}
function Jambes() {
    basic.showLeds(`
        . . # . .
        # # # # #
        . . # . .
        . # . # .
        # . . . #
        `)
    basic.pause(400)
}
basic.showLeds(`
    . . # . .
    . # # # .
    . # # # .
    . # . # .
    # . . . #
    `)
input.onButtonPressed(Button.A, function () {
    Bras()
})
input.onButtonPressed(Button.B, function () {
    Jambes()
})
input.onButtonPressed(Button.AB, function () {
    for (let index = 0; index < 6; index++) {
        Bras()
        Jambes()
    }
})
```

## Étape 10 — Vérifier sur le simulateur

🖥️ Teste l'animation complète !

➡️ Vérifie que le personnage s'affiche bien au repos au démarrage.

➡️ Appuie sur **A** — une pose. Appuie sur **B** — l'autre pose. Appuie sur **A+B** — l'animation complète !

> ❓ L'animation est-elle fluide ? Modifie la valeur des pauses dans tes fonctions pour accélérer ou ralentir le personnage.

## Étape 11 — Télécharger et tester

💾 Envoie ton programme sur le micro:bit !

➡️ Clique sur le bouton **Télécharger** pour transférer ton programme.

➡️ Appuie sur **A+B** et fais des jumping jacks en même temps que le personnage !

## Étape 12 — Question réflexive 🤔

❓ **Combien de fois as-tu dessiné le personnage avec les bras levés dans tout ton programme ?**

❓ **Combien de fois ce dessin s'affiche-t-il quand tu appuies sur A+B ?**

> 💡 Tu n'as dessiné chaque pose **qu'une seule fois** — à l'intérieur de sa fonction. Mais lors de l'animation, chaque pose s'affiche **6 fois** ! Écrire une fois, utiliser partout !

## Étape 13 — Défi de base 🧠

➡️ Modifie la valeur des pauses dans tes fonctions pour changer la vitesse de l'animation.

> ❓ Quelle valeur donne l'animation la plus réaliste ? Essaie `200`, `600`, `800`…

## Étape 14 — Défi avancé 🧠

➡️ Crée une troisième fonction `Gym` qui affiche le personnage debout, bras le long du corps.

➡️ Dans la boucle du bouton **A+B**, appelle `Gym` à la toute fin, après les 6 jumping jacks.

```blocks
function Bras() {
    basic.showLeds(`
        # . # . #
        . # # # .
        . . # . .
        . # . # .
        # . . . #
        `)
    basic.pause(400)
}
function Jambes() {
    basic.showLeds(`
        . . # . .
        # # # # #
        . . # . .
        . # . # .
        # . . . #
        `)
    basic.pause(400)
}
function Gym() {
    basic.showLeds(`
        . . # . .
        . # # # .
        . # # # .
        . # . # .
        # . . . #
        `)
}
basic.showLeds(`
    . . # . .
    . # # # .
    . # # # .
    . # . # .
    # . . . #
    `)
input.onButtonPressed(Button.A, function () {
    Bras()
})
input.onButtonPressed(Button.B, function () {
    Jambes()
})
input.onButtonPressed(Button.AB, function () {
    for (let index = 0; index < 6; index++) {
        Bras()
        Jambes()
    }
    Gym()
})
```

> ❓ Que se passe-t-il après les 6 jumping jacks ? Le personnage est-il bien de retour à sa position de repos ?

🚀 Bravo ! Tu sais maintenant créer et appeler des fonctions — ton personnage fait de l'exercice grâce à ton programme !
