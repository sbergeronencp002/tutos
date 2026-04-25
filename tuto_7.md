# Tutoriel 7 — Pierre, papier, ciseaux !

## @showdialog

🎯 **Objectif** : joue à pierre, papier, ciseaux contre le micro:bit !

Dans ce tutoriel, tu vas découvrir les **conditions** — des blocs qui permettent à ton programme de prendre des décisions selon la situation.

C'est parti ! 🚀

## Étape 1 — Préparer l'espace de travail

🧹 Fais le ménage !

➡️ Supprime le bloc ``||basic:toujours||``.

> 💡 On garde le bloc ``||basic:au démarrage||`` — on va s'en servir à l'étape suivante !

## Étape 2 — Créer une variable

✨ Crée une variable !

➡️ Clique sur **Variables** dans le menu, puis sur **Créer une variable**.

➡️ Nomme-la `choix`.

➡️ Glisse le bloc ``||variables:définir choix à 0||`` à l'intérieur du bloc ``||basic:au démarrage||``.

> 💡 La variable `choix` va mémoriser le résultat du tirage au sort — `1` pour pierre, `2` pour papier, `3` pour ciseaux.

```blocks
let choix = 0
```

## Étape 3 — Tirer au sort

✨ Ajoute une séquence !

➡️ Glisse le bloc ``||variables:définir choix à 0||`` à l'intérieur du bloc ``||input:lorsque secouer||``.

➡️ Remplace le `0` par le bloc ``||math:choisir au hasard de 1 à 4||``.

➡️ Remplace la valeur `4` par `3`.

> 💡 Le bloc **choisir au hasard** tire un nombre entre `1` et `3` — comme lancer un dé ! À chaque secousse, le micro:bit choisit un nombre différent.

> ℹ️ Ne t'inquiète pas si rien ne s'affiche encore — on va ajouter les conditions aux étapes suivantes !

```blocks
let choix = 0
input.onGesture(Gesture.Shake, function () {
    choix = Math.randomRange(1, 3)
})
```

## Étape 4 — Première condition : la pierre 🪨

✨ Nouvelle notion : la **condition** !

➡️ Glisse un bloc ``||logic:si vrai alors||`` sous le bloc ``||variables:définir choix||``.

➡️ Dans la case de la condition, glisse le bloc de comparaison ``||logic:0 = 0||``.

➡️ Dans la partie gauche, insère la variable `choix`. Dans la partie droite, écris `1`.

➡️ À l'intérieur de la condition, glisse le bloc ``||basic:montrer LEDs||`` et reproduis le dessin de la pierre ci-dessous.

> 💡 Une condition pose une question : *"Est-ce que `choix` est égal à `1` ?"*. Si la réponse est **oui**, le programme affiche la pierre. Sinon, il passe à la suite !

```blocks
let choix = 0
input.onGesture(Gesture.Shake, function () {
    choix = Math.randomRange(1, 3)
    if (choix == 1) {
        basic.showLeds(`
            . . . . .
            . # # # .
            . # # # .
            . # # # .
            . . . . .
            `)
    }
})
```

## Étape 5 — Deuxième condition : le papier 📄

➡️ Glisse un deuxième bloc ``||logic:si vrai alors||`` sous le premier.

➡️ Dans la case de la condition, glisse le bloc de comparaison ``||logic:0 = 0||``.

➡️ Dans la partie gauche, insère la variable `choix`. Dans la partie droite, écris `2`.

➡️ À l'intérieur de la condition, glisse le bloc ``||basic:montrer LEDs||`` et reproduis le dessin du papier ci-dessous.

> 💡 Cette deuxième condition pose la question : *"Est-ce que `choix` est égal à `2` ?"*. Si oui, le programme affiche le papier !

```blocks
let choix = 0
input.onGesture(Gesture.Shake, function () {
    choix = Math.randomRange(1, 3)
    if (choix == 1) {
        basic.showLeds(`
            . . . . .
            . # # # .
            . # # # .
            . # # # .
            . . . . .
            `)
    }
    if (choix == 2) {
        basic.showLeds(`
            # # # # #
            # . . . #
            # . . . #
            # . . . #
            # # # # #
            `)
    }
})
```

## Étape 6 — Troisième condition : les ciseaux ✂️

➡️ Glisse un troisième bloc ``||logic:si vrai alors||`` sous le deuxième.

➡️ Dans la case de la condition, glisse le bloc de comparaison ``||logic:0 = 0||``.

➡️ Dans la partie gauche, insère la variable `choix`. Dans la partie droite, écris `3`.

➡️ À l'intérieur de la condition, glisse le bloc ``||basic:montrer LEDs||`` et reproduis le dessin des ciseaux ci-dessous.

> 💡 Le programme vérifie maintenant trois conditions une par une. Il n'entre dans une condition que si elle est **vraie** !

```blocks
let choix = 0
input.onGesture(Gesture.Shake, function () {
    choix = Math.randomRange(1, 3)
    if (choix == 1) {
        basic.showLeds(`
            . . . . .
            . # # # .
            . # # # .
            . # # # .
            . . . . .
            `)
    }
    if (choix == 2) {
        basic.showLeds(`
            # # # # #
            # . . . #
            # . . . #
            # . . . #
            # # # # #
            `)
    }
    if (choix == 3) {
        basic.showLeds(`
            # # . # #
            # # . # #
            . . # . .
            . . # . .
            . . # . .
            `)
    }
})
```

## Étape 7 — Vérifier sur le simulateur

🖥️ Observe le résultat avant de télécharger !

➡️ Vérifie que ton programme fonctionne correctement sur le **simulateur**.

➡️ Teste la secousse sur le **simulateur** en cliquant sur le bouton **SHAKE** plusieurs fois.

> ❓ Est-ce que les trois dessins apparaissent bien ? Modifie les blocs au besoin.

## Étape 8 — Télécharger et tester

💾 Envoie ton programme sur le micro:bit !

➡️ Clique sur le bouton **Télécharger** pour transférer ton programme.

➡️ Secoue ton micro:bit et joue contre un ami !

## Étape 9 — Question réflexive 🤔

❓ **Le programme vérifie-t-il les trois conditions à chaque secousse, ou s'arrête-t-il dès qu'il en trouve une vraie ?**

> 💡 Avec trois blocs ``||logic:si||`` séparés, le programme vérifie **toujours** les trois conditions une par une — même si la première est vraie. C'est différent du **sinon si**, qui s'arrête dès qu'une condition est vraie !

## Étape 10 — Défi supplémentaire 🧠

**Défi de base :**

➡️ Améliore les dessins de la pierre, du papier et des ciseaux pour qu'ils soient plus reconnaissables.

> ❓ Peux-tu dessiner des ciseaux ouverts et des ciseaux fermés en alternance pour créer une petite animation ?

**Défi avancé :**

➡️ Ajoute un bloc ``||basic:afficher texte||`` après chaque dessin pour afficher le nom du choix (`"Pierre"`, `"Papier"` ou `"Ciseaux"`).

```blocks
let choix = 0
input.onGesture(Gesture.Shake, function () {
    choix = Math.randomRange(1, 3)
    if (choix == 1) {
        basic.showLeds(`
            . . . . .
            . # # # .
            . # # # .
            . # # # .
            . . . . .
            `)
        basic.showString("Pierre")
    }
    if (choix == 2) {
        basic.showLeds(`
            # # # # #
            # . . . #
            # . . . #
            # . . . #
            # # # # #
            `)
        basic.showString("Papier")
    }
    if (choix == 3) {
        basic.showLeds(`
            # # . # #
            # # . # #
            . . # . .
            . . # . .
            . . # . .
            `)
        basic.showString("Ciseaux")
    }
})
```

> ❓ Que se passe-t-il si tu secoues le micro:bit pendant que le texte défile ?

🚀 Bravo ! Tu sais maintenant utiliser les conditions pour que ton programme prenne des décisions !