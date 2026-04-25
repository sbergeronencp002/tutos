# Tutoriel 8 — Le dé numérique

## @showdialog

🎯 **Objectif** : transforme ton micro:bit en dé numérique !

Dans ce tutoriel, tu vas consolider ce que tu as appris sur les variables, le hasard et les conditions — mais avec un défi plus grand : six faces à programmer !

C'est parti ! 🚀

## Étape 1 — Préparer l'espace de travail

🧹 Fais le ménage !

➡️ Supprime le bloc ``||basic:toujours||``.

> 💡 On garde le bloc ``||basic:au démarrage||`` — on va s'en servir à l'étape suivante !

## Étape 2 — Créer une variable

✨ Crée une variable !

➡️ Clique sur **Variables** dans le menu, puis sur **Créer une variable**.

➡️ Nomme-la `face`.

➡️ Glisse le bloc ``||variables:définir face à 0||`` à l'intérieur du bloc ``||basic:au démarrage||``.

> 💡 La variable `face` va mémoriser le résultat du lancer — un nombre entre `1` et `6`, comme un vrai dé !

```blocks
let face = 0
```

## Étape 3 — Lancer le dé

✨ Ajoute une séquence !

➡️ Glisse le bloc ``||variables:définir face à 0||`` à l'intérieur du bloc ``||input:lorsque secouer||``.

➡️ Remplace le `0` par le bloc ``||math:choisir au hasard de 1 à 4||``.

➡️ Remplace la valeur `4` par `6`.

> 💡 À chaque secousse, le micro:bit tire un nombre entre `1` et `6` — exactement comme lancer un vrai dé !

> ℹ️ Ne t'inquiète pas si rien ne s'affiche encore — on va ajouter les conditions aux étapes suivantes !

```blocks
let face = 0
input.onGesture(Gesture.Shake, function () {
    face = Math.randomRange(1, 6)
})
```

## Étape 4 — Les six conditions

✨ Ajoute six conditions !

➡️ Glisse six blocs ``||logic:si vrai alors||`` les uns sous les autres dans la séquence ``||input:lorsque secouer||``.

➡️ Dans chaque condition, glisse le bloc de comparaison ``||logic:0 = 0||``.

➡️ Configure chaque condition avec la variable `face` et les valeurs `1` à `6`.

> 💡 Chaque condition correspond à une face du dé. Le programme les vérifie une par une à chaque secousse !

## Étape 5 — Dessiner les six faces

🎨 Reproduis chaque dessin dans la bonne condition !

➡️ Glisse un bloc ``||basic:montrer LEDs||`` à l'intérieur de chacune des six conditions.

➡️ Reproduis les dessins ci-dessous.

```blocks
let face = 0
input.onGesture(Gesture.Shake, function () {
    face = Math.randomRange(1, 6)
    if (face == 1) {
        basic.showLeds(`
            . . . . .
            . . . . .
            . . # . .
            . . . . .
            . . . . .
            `)
    }
    if (face == 2) {
        basic.showLeds(`
            . . . . .
            . # . . .
            . . . . .
            . . . # .
            . . . . .
            `)
    }
    if (face == 3) {
        basic.showLeds(`
            # . . . .
            . . . . .
            . . # . .
            . . . . .
            . . . . #
            `)
    }
    if (face == 4) {
        basic.showLeds(`
            . . . . .
            . # . # .
            . . . . .
            . # . # .
            . . . . .
            `)
    }
    if (face == 5) {
        basic.showLeds(`
            . . . . .
            . # . # .
            . . # . .
            . # . # .
            . . . . .
            `)
    }
    if (face == 6) {
        basic.showLeds(`
            . . . . .
            . # . # .
            . # . # .
            . # . # .
            . . . . .
            `)
    }
})
```

## Étape 6 — Vérifier sur le simulateur

🖥️ Observe le résultat avant de télécharger !

➡️ Vérifie que ton programme fonctionne correctement sur le **simulateur**.

➡️ Teste la secousse sur le **simulateur** en cliquant sur le bouton **SHAKE** plusieurs fois.

> ❓ Est-ce que les six faces apparaissent bien ? Modifie les blocs au besoin.

## Étape 7 — Télécharger et tester

💾 Envoie ton programme sur le micro:bit !

➡️ Clique sur le bouton **Télécharger** pour transférer ton programme.

➡️ Secoue ton micro:bit et joue avec un ami !

## Étape 8 — Question réflexive 🤔

❓ **Tu as programmé six conditions cette fois-ci, au lieu de trois comme dans le tutoriel précédent. Qu'est-ce que ça change dans ton programme ?**

> 💡 Rien de fondamental — le principe est exactement le même ! Plus il y a de cas possibles, plus on ajoute de conditions. C'est la puissance des conditions : elles s'adaptent à n'importe quelle situation.

## Étape 9 — Défi supplémentaire 🧠

**Défi de base :**

➡️ Améliore les dessins des six faces pour qu'ils ressemblent encore plus à un vrai dé.

> ❓ Les points sont-ils bien placés par rapport à un vrai dé ?

**Défi avancé :**

➡️ Ajoute une animation de "lancer" avant d'afficher le résultat.

➡️ Glisse un bloc ``||loops:répéter 4 fois||`` au début de la séquence ``||input:lorsque secouer||``, avant les conditions.

➡️ La valeur `4` demeure la même.

➡️ À l'intérieur de la boucle, glisse le bloc ``||basic:montrer l'icône||`` et choisis trois icônes de ton choix.

➡️ Glisse ensuite un bloc ``||basic:pause (ms) 100||`` après chaque icône.

> 💡 La boucle fait défiler rapidement une icône avant d'afficher le résultat — ça simule le mouvement du dé qui roule !

```blocks
let face = 0
input.onGesture(Gesture.Shake, function () {
    face = Math.randomRange(1, 6)
    for (let index = 0; index < 10; index++) {
        basic.showIcon(IconNames.Square)
        basic.pause(100)
        basic.showIcon(IconNames.Diamond)
        basic.pause(100)
        basic.showIcon(IconNames.SmallDiamond)
        basic.pause(100)
    }
    if (face == 1) {
        basic.showLeds(`
            . . . . .
            . . . . .
            . . # . .
            . . . . .
            . . . . .
            `)
    }
    if (face == 2) {
        basic.showLeds(`
            . . . . .
            . # . . .
            . . . . .
            . . . # .
            . . . . .
            `)
    }
    if (face == 3) {
        basic.showLeds(`
            # . . . .
            . . . . .
            . . # . .
            . . . . .
            . . . . #
            `)
    }
    if (face == 4) {
        basic.showLeds(`
            . . . . .
            . # . # .
            . . . . .
            . # . # .
            . . . . .
            `)
    }
    if (face == 5) {
        basic.showLeds(`
            . . . . .
            . # . # .
            . . # . .
            . # . # .
            . . . . .
            `)
    }
    if (face == 6) {
        basic.showLeds(`
            . . . . .
            . # . # .
            . # . # .
            . # . # .
            . . . . .
            `)
    }
})

```

> ❓ Que se passe-t-il si tu changes la valeur de la pause à `50` ? Et à `300` ?

🚀 Bravo ! Tu sais maintenant combiner variables, hasard et conditions pour créer un dé numérique !