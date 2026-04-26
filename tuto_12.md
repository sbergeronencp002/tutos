# Tutoriel 12 — Le capteur de luminosité 💡

## @showdialog

🎯 **Objectif** : fais réagir ton micro:bit selon la luminosité ambiante !

Dans ce tutoriel, tu vas découvrir le **capteur de luminosité** du micro:bit — il peut détecter si tu es dans une pièce éclairée ou dans le noir !

C'est parti ! 🚀

## Étape 1 — Préparer l'espace de travail

🧹 Fais le ménage !

➡️ Supprime le bloc ``||basic:au démarrage||``.

> 💡 Cette fois, on garde le bloc ``||basic:toujours||`` — le micro:bit va lire la luminosité en continu, sans arrêt !

## Étape 2 — Lire la luminosité

✨ Nouvelle notion : le **capteur de luminosité** !

➡️ Glisse le bloc ``||basic:afficher nombre||`` à l'intérieur du bloc ``||basic:toujours||``.

➡️ Dans le bloc ``||basic:afficher nombre||``, insère le bloc ``||input:niveau d'intensité lumineuse||``.

> 💡 Le micro:bit utilise ses LEDs comme capteur de luminosité — il mesure la quantité de lumière qui l'atteint et retourne un nombre entre `0` (noir total) et `255` (très lumineux) !

```blocks
basic.forever(function () {
    basic.showNumber(input.lightLevel())
})
```

## Étape 3 — Observer les valeurs

🔬 Fais une petite expérience !

➡️ Vérifie que ton programme fonctionne sur le **simulateur**.

➡️ Fais glisser le curseur de luminosité sous le simulateur et observe les valeurs qui changent.

> ❓ Quelle valeur obtiens-tu quand le curseur est au minimum ? Et au maximum ? Note ces valeurs — tu en auras besoin à l'étape suivante !

## Étape 4 — Ajouter la première condition ☀️

✨ Réagis à une luminosité élevée !

➡️ Remplace le bloc ``||basic:afficher nombre||`` par un bloc ``||logic:si vrai alors||``.

➡️ Dans la case de la condition, glisse le bloc de comparaison ``||logic:0 > 0||``.

➡️ Dans la partie gauche, insère le bloc ``||input:niveau d'intensité lumineuse||``. Dans la partie droite, écris `100`.

> 💡 Si la luminosité est **supérieure à `100`**, il fait clair — le micro:bit affichera le soleil ☀️ !

```blocks
basic.forever(function () {
    if (input.lightLevel() > 100) {
    }
})
```

## Étape 5 — Ajouter la deuxième condition 🌙

✨ Réagis à une luminosité faible !

➡️ Glisse un deuxième bloc ``||logic:si vrai alors||`` sous le premier.

➡️ Dans la case de la condition, glisse le bloc de comparaison ``||logic:0 ≤ 0||``.

➡️ Dans la partie gauche, insère le bloc ``||input:niveau d'intensité lumineuse||``. Dans la partie droite, écris `100`.

> 💡 Si la luminosité est **inférieure ou égale à `100`**, il fait sombre — le micro:bit affichera la lune 🌙 !

```blocks
basic.forever(function () {
    if (input.lightLevel() > 100) {
    }
    if (input.lightLevel() <= 100) {
    }
})
```

## Étape 6 — Afficher le soleil ou la lune

🎨 Remplis les conditions !

➡️ À l'intérieur de la première condition (`> 100`), glisse le bloc ``||basic:montrer LEDs||`` et reproduis le dessin du soleil ☀️ ci-dessous.

➡️ À l'intérieur de la deuxième condition (`≤ 100`), glisse le bloc ``||basic:montrer LEDs||`` et reproduis le dessin de la lune 🌙 ci-dessous.

```blocks
basic.forever(function () {
    if (input.lightLevel() > 100) {
        basic.showLeds(`
            . . # . .
            . # # # .
            # # # # #
            . # # # .
            . . # . .
            `)
    }
    if (input.lightLevel() <= 100) {
        basic.showLeds(`
            . . # # .
            . # . . .
            # . . . .
            . # . . .
            . . # # .
            `)
    }
})
```

## Étape 7 — Vérifier sur le simulateur

🖥️ Observe le résultat avant de télécharger !

➡️ Vérifie que ton programme fonctionne correctement sur le **simulateur**.

➡️ Fais glisser le curseur de luminosité sous le simulateur et observe les icônes changer.

> ❓ Est-ce que le soleil et la lune s'affichent bien selon la luminosité ? Modifie les blocs au besoin.

## Étape 8 — Télécharger et tester

💾 Envoie ton programme sur le micro:bit !

➡️ Clique sur le bouton **Télécharger** pour transférer ton programme.

➡️ Cache le micro:bit sous ta main et observe l'écran.

➡️ Pointe le micro:bit vers une source lumineuse et observe à nouveau.

> 💡 Si le micro:bit ne réagit pas correctement, ajuste la valeur `100` selon les observations que tu as faites à l'étape 3 !

## Étape 9 — Question réflexive 🤔

❓ **Que se passe-t-il si tu utilises exactement la valeur `100` comme seuil — est-ce que le micro:bit affiche le soleil ou la lune ?**

❓ **Pourquoi est-il important d'observer les valeurs réelles du capteur avant de choisir un seuil ?**

> 💡 Chaque environnement est différent — une salle de classe bien éclairée n'a pas la même luminosité qu'une pièce sombre. C'est pourquoi on observe d'abord les valeurs avant de choisir le seuil !

## Étape 10 — Défi de base 🧠

➡️ Modifie le seuil de `100` pour qu'il corresponde mieux à la luminosité de ta classe.

> ❓ Quelle valeur donne le meilleur résultat dans ton environnement ?

## Étape 11 — Défi avancé 🧠

➡️ Ajoute une troisième condition pour une luminosité **moyenne** — affiche une icône différente quand la luminosité est entre `50` et `150`.

```blocks
basic.forever(function () {
    if (input.lightLevel() > 150) {
        basic.showLeds(`
            . . # . .
            . # # # .
            # # # # #
            . # # # .
            . . # . .
            `)
    }
    if (input.lightLevel() <= 150 && input.lightLevel() > 50) {
        basic.showIcon(IconNames.Triangle)
    }
    if (input.lightLevel() <= 50) {
        basic.showLeds(`
            . . # # .
            . # . . .
            # . . . .
            . # . . .
            . . # # .
            `)
    }
})
```

> ❓ Est-ce que les trois zones de luminosité sont bien distinctes ?

🚀 Bravo ! Tu sais maintenant utiliser le capteur de luminosité pour faire réagir ton micro:bit à son environnement !