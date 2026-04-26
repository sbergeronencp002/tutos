# Tutoriel 13 — Le capteur de température 🌡️

## @showdialog

🎯 **Objectif** : fais réagir ton micro:bit selon la température ambiante !

Dans ce tutoriel, tu vas découvrir le **capteur de température** du micro:bit — il peut détecter s'il fait chaud ou froid autour de lui !

C'est parti ! 🚀

## Étape 1 — Préparer l'espace de travail

🧹 Fais le ménage !

➡️ Supprime le bloc ``||basic:au démarrage||``.

> 💡 Comme au tutoriel précédent, on garde le bloc ``||basic:toujours||`` — le micro:bit va lire la température en continu !

## Étape 2 — Lire la température

✨ Nouvelle notion : le **capteur de température** !

➡️ Glisse le bloc ``||basic:afficher nombre||`` à l'intérieur du bloc ``||basic:toujours||``.

➡️ Dans le bloc ``||basic:afficher nombre||``, insère le bloc ``||input:température (°C)||``.

> 💡 Le micro:bit mesure la température de son processeur — elle est généralement un peu plus élevée que la température ambiante réelle, mais elle varie de la même façon !

```blocks
basic.forever(function () {
    basic.showNumber(input.temperature())
})
```

## Étape 3 — Observer les valeurs

🔬 Fais une petite expérience !

➡️ Vérifie que ton programme fonctionne sur le **simulateur**.

➡️ Fais glisser le curseur de température sous le simulateur et observe les valeurs qui changent.

> ❓ Quelle valeur obtiens-tu quand le curseur est au minimum ? Et au maximum ? Note ces valeurs — tu en auras besoin à l'étape suivante !

## Étape 4 — Ajouter la première condition 🌞

✨ Réagis à une température élevée !

➡️ Remplace le bloc ``||basic:afficher nombre||`` par un bloc ``||logic:si vrai alors||``.

➡️ Dans la case de la condition, glisse le bloc de comparaison ``||logic:0 > 0||``.

➡️ Dans la partie gauche, insère le bloc ``||input:température (°C)||``. Dans la partie droite, écris `20`.

> 💡 Si la température est **supérieure à `20°C`**, il fait chaud — le micro:bit affichera le soleil 🌞 !

```blocks
basic.forever(function () {
    if (input.temperature() > 20) {
    }
})
```

## Étape 5 — Ajouter la deuxième condition ❄️

✨ Réagis à une température froide !

➡️ Glisse un deuxième bloc ``||logic:si vrai alors||`` sous le premier.

➡️ Dans la case de la condition, glisse le bloc de comparaison ``||logic:0 ≤ 0||``.

➡️ Dans la partie gauche, insère le bloc ``||input:température (°C)||``. Dans la partie droite, écris `20`.

> 💡 Si la température est **inférieure ou égale à `20°C`**, il fait frais — le micro:bit affichera un flocon de neige ❄️ !

```blocks
basic.forever(function () {
    if (input.temperature() > 20) {
    }
    if (input.temperature() <= 20) {
    }
})
```

## Étape 6 — Afficher le soleil ou le flocon

🎨 Remplis les conditions !

➡️ À l'intérieur de la première condition (`> 20`), glisse le bloc ``||basic:montrer LEDs||`` et reproduis le dessin du soleil 🌞 ci-dessous.

➡️ À l'intérieur de la deuxième condition (`≤ 20`), glisse le bloc ``||basic:montrer LEDs||`` et reproduis le dessin du flocon ❄️ ci-dessous.

```blocks
basic.forever(function () {
    if (input.temperature() > 20) {
        basic.showLeds(`
            . . # . .
            . # # # .
            # # # # #
            . # # # .
            . . # . .
            `)
    }
    if (input.temperature() <= 20) {
        basic.showLeds(`
            # . # . #
            . # # # .
            # # # # #
            . # # # .
            # . # . #
            `)
    }
})
```

## Étape 7 — Vérifier sur le simulateur

🖥️ Observe le résultat avant de télécharger !

➡️ Vérifie que ton programme fonctionne correctement sur le **simulateur**.

➡️ Fais glisser le curseur de température sous le simulateur et observe les icônes changer.

> ❓ Est-ce que le soleil et le flocon s'affichent bien selon la température ? Modifie les blocs au besoin.

## Étape 8 — Télécharger et tester

💾 Envoie ton programme sur le micro:bit !

➡️ Clique sur le bouton **Télécharger** pour transférer ton programme.

➡️ Tiens le micro:bit dans ta main et observe l'écran — la chaleur de ta main devrait faire monter la température !

➡️ Pose le micro:bit sur une surface froide et observe à nouveau.

> 💡 Si le micro:bit ne réagit pas correctement, ajuste la valeur `20` selon la température de ta classe !

## Étape 9 — Question réflexive 🤔

❓ **Pourquoi la température mesurée par le micro:bit est-elle différente de la température réelle de la pièce ?**

❓ **Comment pourrais-tu utiliser ce capteur dans un projet utile dans la vraie vie ?**

> 💡 Le capteur mesure la chaleur du processeur — mais comme il est influencé par la température ambiante, il reste un bon indicateur ! Dans la vraie vie, ce principe est utilisé dans les thermostats, les serres agricoles, et même les vêtements intelligents !

## Étape 10 — Défi de base 🧠

➡️ Modifie le seuil de `20` pour qu'il corresponde mieux à la température de ta classe.

> ❓ Quelle valeur donne le meilleur résultat dans ton environnement ?

## Étape 11 — Défi avancé 🧠

➡️ Ajoute une troisième condition pour une température **moyenne** — affiche une icône différente quand la température est entre `20` et `25`.

```blocks
basic.forever(function () {
    if (input.temperature() > 25) {
        basic.showLeds(`
            . . # . .
            . # # # .
            # # # # #
            . # # # .
            . . # . .
            `)
    }
    if (input.temperature() <= 25 && input.temperature() > 20) {
        basic.showIcon(IconNames.Happy)
    }
    if (input.temperature() <= 20) {
        basic.showLeds(`
            # . # . #
            . # # # .
            # # # # #
            . # # # .
            # . # . #
            `)
    }
})
```

> ❓ Est-ce que les trois zones de température sont bien distinctes dans ta classe ?

🚀 Bravo ! Tu sais maintenant utiliser le capteur de température pour faire réagir ton micro:bit à son environnement !