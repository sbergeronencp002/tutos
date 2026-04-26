# Tutoriel 10 — La boule magique 🎱

## @showdialog

🎯 **Objectif** : transforme ton micro:bit en boule magique qui répond à toutes tes questions !

Dans ce tutoriel, tu vas consolider tout ce que tu as appris — variables, hasard et conditions — dans un projet mystérieux et amusant !

C'est parti ! 🚀

## Étape 1 — Préparer l'espace de travail

🧹 Fais le ménage !

➡️ Supprime le bloc ``||basic:toujours||``.

> 💡 On garde le bloc ``||basic:au démarrage||`` — on va s'en servir à l'étape suivante !

## Étape 2 — Créer une variable

✨ Crée une variable !

➡️ Clique sur **Variables** dans le menu, puis sur **Créer une variable**.

➡️ Nomme-la `reponse`.

➡️ Glisse le bloc ``||variables:définir reponse à 0||`` à l'intérieur du bloc ``||basic:au démarrage||``.

> 💡 La variable `reponse` va mémoriser le numéro de la réponse choisie au hasard — un nombre entre `1` et `5` !

```blocks
let reponse = 0
```

## Étape 3 — Afficher la boule magique

✨ Ajoute une image de départ !

➡️ Glisse le bloc ``||basic:montrer LEDs||`` sous le bloc ``||variables:définir reponse à 0||`` dans le bloc ``||basic:au démarrage||``.

➡️ Reproduis le dessin de la boule magique ci-dessous.

> 💡 Au démarrage, le micro:bit affiche la boule magique — il attend ta question !

```blocks
let reponse = 0
basic.showLeds(`
    . # # # .
    # # # # #
    # # # # #
    . # # # .
    . . # . .
    `)
```

## Étape 4 — Tirer une réponse au hasard

✨ Ajoute une séquence !

➡️ Glisse le bloc ``||variables:définir reponse à 0||`` à l'intérieur du bloc ``||input:lorsque secouer||``.

➡️ Remplace le `0` par le bloc ``||math:choisir au hasard de 1 à 4||``.

➡️ Remplace la valeur `4` par `5`.

> 💡 À chaque secousse, le micro:bit choisit un nombre entre `1` et `5` — chaque nombre correspond à une réponse différente !

> ℹ️ Ne t'inquiète pas si rien ne s'affiche encore — on va ajouter les conditions aux étapes suivantes !

```blocks
let reponse = 0
input.onGesture(Gesture.Shake, function () {
    reponse = Math.randomRange(1, 5)
})
```

## Étape 5 — Les cinq conditions

✨ Ajoute cinq conditions !

➡️ Glisse cinq blocs ``||logic:si vrai alors||`` les uns sous les autres dans la séquence ``||input:lorsque secouer||``.

➡️ Dans chaque condition, glisse le bloc de comparaison ``||logic:0 = 0||``.

➡️ Configure chaque condition avec la variable `reponse` et les valeurs `1` à `5`.

> 💡 Chaque condition correspond à une réponse de la boule magique. Le programme vérifie les conditions une par une à chaque secousse !

```blocks
let reponse = 0
input.onGesture(Gesture.Shake, function () {
    reponse = Math.randomRange(1, 5)
    if (reponse == 1) {
    }
    if (reponse == 2) {
    }
    if (reponse == 3) {
    }
    if (reponse == 4) {
    }
    if (reponse == 5) {
    }
})
```

## Étape 6 — Ajouter les réponses

🎱 Remplis chaque condition avec une réponse !

➡️ Glisse un bloc ``||basic:afficher texte||`` à l'intérieur de chacune des cinq conditions.

➡️ Écris une réponse différente dans chaque bloc :
- Condition `1` → `"Oui !"`
- Condition `2` → `"Non !"`
- Condition `3` → `"Peut-etre"`
- Condition `4` → `"Surement"`
- Condition `5` → `"Jamais !"`

> 💡 Rappel : évite les accents dans les textes pour un affichage correct sur le micro:bit !

```blocks
let reponse = 0
input.onGesture(Gesture.Shake, function () {
    reponse = Math.randomRange(1, 5)
    if (reponse == 1) {
        basic.showString("Oui !")
    }
    if (reponse == 2) {
        basic.showString("Non !")
    }
    if (reponse == 3) {
        basic.showString("Peut-etre")
    }
    if (reponse == 4) {
        basic.showString("Surement")
    }
    if (reponse == 5) {
        basic.showString("Jamais !")
    }
})
```

## Étape 7 — Vérifier sur le simulateur

🖥️ Observe le résultat avant de télécharger !

➡️ Vérifie que ton programme fonctionne correctement sur le **simulateur**.

➡️ Teste la secousse sur le **simulateur** en cliquant sur le bouton **SHAKE** plusieurs fois.

> ❓ Est-ce que les cinq réponses apparaissent bien ? Modifie les blocs au besoin.

## Étape 8 — Télécharger et tester

💾 Envoie ton programme sur le micro:bit !

➡️ Clique sur le bouton **Télécharger** pour transférer ton programme.

➡️ Pense à une question, secoue ton micro:bit et découvre la réponse de la boule magique !

## Étape 9 — Question réflexive 🤔

❓ **Est-ce que toutes les réponses ont autant de chances d'apparaître ?**

❓ **Que se passerait-il si tu changeais `choisir au hasard de 1 à 5` par `choisir au hasard de 1 à 3` ?**

> 💡 Avec `choisir au hasard de 1 à 3`, seules les trois premières conditions pourraient être vraies — les réponses `4` et `5` n'apparaîtraient jamais !

## Étape 10 — Défi de base 🧠

➡️ Remplace les réponses textuelles par des icônes ou des dessins en utilisant le bloc ``||basic:montrer l'icône||`` ou ``||basic:montrer LEDs||``.

> ❓ Peux-tu dessiner un visage heureux pour "Oui" et un visage triste pour "Non" ?

## Étape 11 — Défi avancé 🧠

➡️ Ajoute une animation de "consultation" avant d'afficher la réponse : fais défiler des points de suspension `"..."` avec une pause, pour faire patienter l'utilisateur.

➡️ Ajoute ensuite la boule magique ``||basic:montrer LEDs||`` à la fin, après la réponse, pour que le micro:bit soit prêt pour la prochaine question.

```blocks
let reponse = 0
input.onGesture(Gesture.Shake, function () {
    reponse = Math.randomRange(1, 5)
    basic.showString("...")
    basic.pause(500)
    if (reponse == 1) {
        basic.showString("Oui !")
    }
    if (reponse == 2) {
        basic.showString("Non !")
    }
    if (reponse == 3) {
        basic.showString("Peut-etre")
    }
    if (reponse == 4) {
        basic.showString("Surement")
    }
    if (reponse == 5) {
        basic.showString("Jamais !")
    }
    basic.showLeds(`
        . # # # .
        # # # # #
        # # # # #
        . # # # .
        . . # . .
        `)
})
```

> ❓ Que se passe-t-il si tu augmentes la pause à `2000` ? L'effet est-il plus mystérieux ?

🚀 Bravo ! Tu as terminé les dix premiers tutoriels — tu maîtrises maintenant les bases de la programmation avec le micro:bit !