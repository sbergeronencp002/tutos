# Tutoriel 2 — Afficher une icône

## @showdialog

🎯 **Objectif** : fais afficher une icône sur l'écran du micro:bit !

Dans ce tutoriel, tu vas découvrir le bloc **montrer l'icône** et créer une petite animation.

C'est parti ! 🚀

## Étape 1 — Choisir une icône

✨ Ajoute un bloc à ton programme !

➡️ Glisse le bloc ``||basic:montrer l'icône||`` à l'intérieur du bloc ``||basic:toujours||``.

➡️ Clique sur l'icône dans le bloc pour choisir celle que tu préfères.

> 💡 Appuie sur la flèche ⬇️ pour voir toutes les icônes disponibles !

```blocks
basic.forever(function () {
    basic.showIcon(IconNames.Heart)
})
```

## Étape 2 — Vérifier sur le simulateur

🖥️ Observe le résultat avant de télécharger !

➡️ Vérifie que ton icône s'affiche correctement sur le **simulateur**.

> ❓ Est-ce bien l'icône que tu voulais ?

## Étape 3 — Télécharger le programme

💾 Envoie ton programme sur le micro:bit !

➡️ Clique sur le bouton **Télécharger** pour transférer ton programme.

## Étape 4 — Observer le résultat

👀 Regarde ton micro:bit !

➡️ Observe ton icône s'afficher sur l'écran.

> 🎉 Ça fonctionne ? Bravo ! Passons au défi !

## Étape 5 — Question réflexive 🤔

❓ **Que se passe-t-il si tu n'ajoutes pas de pause entre les icônes dans une animation ?**

❓ **Quelle différence y a-t-il entre afficher une icône et afficher un texte sur le micro:bit ?**

> 💡 Sans pause, les icônes changent si vite qu'on ne peut pas les distinguer — l'animation devient floue ! Une icône est une image prédéfinie, tandis qu'un texte fait défiler des caractères un par un.

## Étape 6 — Défi de base 🧠

➡️ Ajoute **deux autres** blocs ``||basic:montrer l'icône||`` pour afficher trois icônes différentes en séquence.

💡 Les icônes s'enchaîneront automatiquement en boucle — c'est une animation !

```blocks
basic.forever(function () {
    basic.showIcon(IconNames.Heart)
    basic.showIcon(IconNames.Silly)
    basic.showIcon(IconNames.LeftTriangle)
})
```

## Étape 7 — Défi avancé 🧠

⏱️ L'animation va trop vite ? Ajoute des pauses !

➡️ Glisse un bloc ``||basic:pause (ms)||`` **entre chaque icône**.

💡 La valeur `500` correspond à une pause de **0,5 seconde**. 

Essaie d'autres valeurs pour accélérer ou ralentir ton animation !

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

🚀 Bravo ! Tu sais maintenant créer une animation avec des icônes sur le micro:bit !