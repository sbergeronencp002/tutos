# Tutoriel 2

## @showdialog

🎯 **Objectif** 🎯 : fais afficher une icône sur l'écran du micro:bit ! 

C'est parti ! 🚀 🚀 🚀

## Étape 1

✨ Ajoute un bloc !

➡️ Ajoute le bloc ``|| basic: montrer l'icône ||`` dans le bloc ``||basic: toujours||``.

Sélectionne une icône de ton choix dans le bloc ``|| basic: montrer l'icône ||``.

Appuie sur la flèche ⬇️ pour afficher les autres choix.

```blocks
basic.forever(function () {
    basic.showIcon(IconNames.Heart)
})

```

## Étape 2

🖥️ Vérifie que ton icône s'affiche correctement sur le simulateur.

## Étape 3

💾 Télécharge la programme sur le micro:bit.

## Étape 4

➡️ Observe ton icône s'afficher sur l'écran du micro:bit. 

## Étape 5

🧠 **Défi supplémentaire** 🧠

✨ Ajoute des blocs !

➡️ Ajoute deux autres blocs ``|| basic: montrer l'icône ||`` pour afficher trois icônes en tout.

Prêt ? C'est parti ! 🚀 🚀 🚀

```blocks

basic.forever(function () {
    basic.showIcon(IconNames.Heart)
    basic.showIcon(IconNames.Silly)
    basic.showIcon(IconNames.LeftTriangle)
})

```

## Étape 6

➡️ Ajoute un bloc ``|| basic: pause (ms) ||`` entre chaque icône pour ralentir l'affichage.

```blocks

basic.forever(function () {
    basic.showIcon(IconNames.Heart)
    basic.pause(500)
    basic.showIcon(IconNames.Silly)
    basic.pause(500)
    basic.showIcon(IconNames.LeftTriangle)
    basic.pause(500)
})

```