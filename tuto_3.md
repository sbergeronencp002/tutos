# Tutoriel 3 — Dessiner sur l'écran

## @showdialog

🎯 **Objectif** : dessine ta propre image sur l'écran du micro:bit !

Dans ce tutoriel, tu vas créer une image personnalisée en allumant toi-même les pixels de l'écran.

C'est parti ! 🚀

## Étape 1 — Ajouter un bloc

✨ Ajoute un bloc à ton programme !

➡️ Glisse le bloc ``||basic:montrer LEDs||`` à l'intérieur du bloc ``||basic:toujours||``.

> 💡 L'écran du micro:bit est une grille de **5 × 5 points lumineux** appelés LEDs. Tu peux allumer ou éteindre chacun d'eux !

```blocks
basic.forever(function () {
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        `)
})
```

## Étape 2 — Dessiner une image

🎨 Crée ton dessin !

➡️ Clique sur les cases du bloc ``||basic:montrer LEDs||`` pour allumer des LEDs.

➡️ Dessine ce que tu veux : une flèche, une maison, un visage, une lettre…

> 💡 Un carré allumé = LED **allumée**. Un carré vide = LED **éteinte**.

```blocks
basic.forever(function () {
    basic.showLeds(`
        . . # . .
        . . # . .
        . . # . .
        . # # # .
        . . # . .
        `)
})
```

## Étape 3 — Vérifier sur le simulateur

🖥️ Observe le résultat avant de télécharger !

➡️ Vérifie que ton image s'affiche correctement sur le **simulateur**.

> ❓ Est-ce bien le dessin que tu voulais ? Retouche les cases si besoin.

## Étape 4 — Télécharger le programme

💾 Envoie ton programme sur le micro:bit !

➡️ Clique sur le bouton **Télécharger** pour transférer ton programme.

## Étape 5 — Observer le résultat

👀 Regarde ton micro:bit !

➡️ Observe ton dessin s'afficher sur l'écran.

> 🎉 Tu as créé ta propre image ! Bravo !

## Étape 6 — Défi : une animation ⚔️🛡️🏹

Tu veux aller plus loin ?

➡️ Ajoute **deux autres** blocs ``||basic:montrer LEDs||`` pour créer une animation avec trois images différentes.

➡️ Ajoute un bloc ``||basic:pause (ms)||`` entre chaque image.

> 💡 Tu connais déjà cette technique depuis le tutoriel sur les icônes — mais cette fois, c'est **toi** qui dessines chaque image !
```blocks
basic.forever(function () {
    basic.showLeds(`
        . . # . .
        . . # . .
        . . # . .
        . # # # .
        . . # . .
        `)
    basic.pause(500)
    basic.showLeds(`
        # # # # #
        # # # # #
        . # # # .
        . # # # .
        . . # . .
        `)
    basic.pause(500)
    basic.showLeds(`
        # . . . #
        # . . # .
        # . # . .
        # . . # .
        # . . . #
        `)
    basic.pause(500)
})
```

🚀 Bravo ! Tu sais maintenant dessiner n'importe quelle image sur le micro:bit !