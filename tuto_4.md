# Tutoriel 4 — Programmer les boutons

## @showdialog

🎯 **Objectif** : affiche différentes images selon le bouton que tu presses sur le micro:bit !

Dans ce tutoriel, tu vas découvrir comment programmer les **boutons A, B et A+B**.

C'est parti ! 🚀

## Étape 1 — Préparer l'espace de travail

🧹 Fais du ménage !

➡️ Supprime les blocs ``||basic:au démarrage||`` et ``||basic:toujours||``.

> 💡 Cette fois, ton programme ne démarre pas tout seul. Il attend que tu appuies sur un bouton — c'est ce qu'on appelle un **événement** !

## Étape 2 — Bouton A : l'épée ⚔️

✨ Ajoute une première séquence !

➡️ Glisse le bloc ``||basic:montrer LEDs||`` à l'intérieur du bloc ``||input:lorsque le bouton A est pressé||``.

➡️ Reproduis le dessin de l'épée ci-dessous.

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showLeds(`
        . . . # #
        # . # # #
        # # # # .
        . # # . .
        # . # # .
        `)
})
```

## Étape 3 — Bouton B : l'armure 🛡️

✨ Ajoute une deuxième séquence !

➡️ Conserve ta première séquence et ajoute-en une nouvelle à côté.

➡️ Glisse le bloc ``||basic:montrer LEDs||`` à l'intérieur du bloc ``||input:lorsque le bouton B est pressé||``.

➡️ Reproduis le dessin de l'armure ci-dessous.

```blocks
input.onButtonPressed(Button.B, function () {
    basic.showLeds(`
        # # . # #
        # # # # #
        . # # # .
        . # # # .
        . . # . .
        `)
})
```

## Étape 4 — Bouton A+B : l'arc 🏹

✨ Ajoute une troisième séquence !

➡️ Conserve tes deux séquences et ajoute-en une nouvelle à côté.

➡️ Glisse le bloc ``||basic:montrer LEDs||`` à l'intérieur du bloc ``||input:lorsque le bouton A+B est pressé||``.

➡️ Reproduis le dessin de l'arc ci-dessous.

> 💡 Pour activer **A+B**, tu dois appuyer sur les deux boutons **en même temps** !

```blocks
input.onButtonPressed(Button.AB, function () {
    basic.showLeds(`
        # # # . #
        . # . # .
        . . # . #
        # # . # #
        . # . . #
        `)
})
```

## Étape 5 — Vérifier sur le simulateur

🖥️ Observe le résultat avant de télécharger !

➡️ Vérifie que ton image s'affiche correctement sur le **simulateur**.

➡️ Appuie sur les **boutons A, B et A+B** du simulateur.

> ❓ Est-ce bien le dessin que tu voulais ? Retouche les cases si besoin.

## Étape 6 — Télécharger et tester

💾 Envoie ton programme sur le micro:bit !

➡️ Clique sur le bouton **Télécharger** pour transférer ton programme.

➡️ Appuie sur les boutons **A**, **B** et **A+B** et observe l'écran.

## Étape 7 — Question réflexive 🤔

❓ **Pourquoi rien ne s'affiche sur le micro:bit au démarrage ?**

❓ **Quelle action dois-tu réaliser pour voir une image ?**

> 💡 Dans les tutoriels précédents, le bloc ``||basic:toujours||`` faisait démarrer le programme automatiquement. Ici, le programme **attend** que tu fasses quelque chose. C'est toi qui contrôles !

## Étape 8 — Défi supplémentaire 🧠

**Défi de base :**

➡️ Remplace les dessins des boutons A, B et A+B par tes propres images.

> ❓ Peux-tu dessiner un bouclier ? Une potion ? Un autre objet de ton choix ?

**Défi avancé :**

➡️ Ajoute un bloc ``||basic:afficher texte||`` après chaque dessin pour afficher le nom de l'objet.

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showLeds(`
        . . . # #
        # . # # #
        # # # # .
        . # # . .
        # . # # .
        `)
    basic.showString("Epee")
})
input.onButtonPressed(Button.B, function () {
    basic.showLeds(`
        # # . # #
        # # # # #
        . # # # .
        . # # # .
        . . # . .
        `)
    basic.showString("Armure")
})
input.onButtonPressed(Button.AB, function () {
    basic.showLeds(`
        # # # . #
        . # . # .
        . . # . #
        # # . # #
        . # . . #
        `)
    basic.showString("Arc")
})
```

> ❓ Que se passe-t-il si tu appuies sur un bouton pendant que le texte défile ?

🚀 Bravo ! Tu sais maintenant programmer les boutons du micro:bit !