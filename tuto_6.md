# Tutoriel 6 — Compter avec une variable

## @showdialog

🎯 **Objectif** : compte le nombre de points avec le micro:bit !

Dans ce tutoriel, tu vas découvrir les **variables** — des cases mémoire qui permettent de stocker et modifier une valeur.

C'est parti ! 🚀

## Étape 1 — Préparer l'espace de travail

🧹 Fais le ménage !

➡️ Supprime le bloc ``||basic:toujours||``.

> 💡 On garde le bloc ``||basic:au démarrage||`` — on va s'en servir à l'étape suivante !

## Étape 2 — Créer une variable

✨ Crée ta première variable !

➡️ Clique sur **Variables** dans le menu, puis sur **Créer une variable**.

➡️ Nomme-la `compteur`.

➡️ Glisse le bloc ``||variables:définir compteur à 0||`` à l'intérieur du bloc ``||basic:au démarrage||``.

> 💡 Une **variable**, c'est comme une case mémoire. On lui donne un nom et on y stocke une valeur. Ici, `compteur` commence à `0`.

```blocks
let compteur = 0
```

## Étape 3 — Bouton A : ajouter un point ➕

✨ Ajoute une séquence !

➡️ Glisse le bloc ``||variables:modifier compteur de 1||`` à l'intérieur du bloc ``||input:lorsque le bouton A est pressé||``.

➡️ Glisse ensuite le bloc ``||basic:afficher nombre||`` en dessous.

➡️ Dans le bloc ``||basic:afficher nombre||``, insère la variable `compteur`.

> 💡 À chaque appui sur **A**, la valeur de `compteur` augmente de `1` et s'affiche sur l'écran !

```blocks
input.onButtonPressed(Button.A, function () {
    compteur += 1
    basic.showNumber(compteur)
})
```

## Étape 4 — Bouton B : retirer un point ➖

✨ Ajoute une deuxième séquence !

➡️ Glisse le bloc ``||variables:modifier compteur de 1||`` à l'intérieur du bloc ``||input:lorsque le bouton B est pressé||``.

➡️ Remplace la valeur `1` par `-1`.

➡️ Glisse ensuite le bloc ``||basic:afficher nombre||`` en dessous avec la variable `compteur`.

> 💡 À chaque appui sur **B**, la valeur de `compteur` diminue de `1`. Tu peux donc corriger une erreur de comptage !

```blocks
input.onButtonPressed(Button.B, function () {
    compteur += -1
    basic.showNumber(compteur)
})
```

## Étape 5 — Bouton A+B : réinitialiser 🔄

✨ Ajoute une troisième séquence !

➡️ Glisse le bloc ``||variables:définir compteur à 0||`` à l'intérieur du bloc ``||input:lorsque le bouton A+B est pressé||``.

➡️ Glisse ensuite le bloc ``||basic:afficher nombre||`` en dessous avec la variable `compteur`.

> 💡 **A+B** remet le compteur à zéro — utile pour recommencer une nouvelle partie !

```blocks
input.onButtonPressed(Button.AB, function () {
    compteur = 0
    basic.showNumber(compteur)
})
```

## Étape 6 — Vérifier sur le simulateur

🖥️ Observe le résultat avant de télécharger !

➡️ Vérifie que ton programme fonctionne correctement sur le **simulateur**.

➡️ Teste les boutons **A**, **B** et **A+B** sur le **simulateur** en cliquant dessus.

> ❓ Est-ce bien le comportement attendu ? Modifie les blocs au besoin.

## Étape 7 — Télécharger et tester

💾 Envoie ton programme sur le micro:bit !

➡️ Clique sur le bouton **Télécharger** pour transférer ton programme.

➡️ Teste les boutons **A**, **B** et **A+B**.

## Étape 8 — Question réflexive 🤔

❓ **Que se passe-t-il si tu appuies sur B avant d'avoir appuyé sur A ?**

❓ **Est-ce que le compteur peut afficher des nombres négatifs ?**

> 💡 Une variable n'a pas de limite — elle peut monter très haut ou descendre en dessous de zéro !

## Étape 9 — Défi supplémentaire 🧠

**Défi de base :**

➡️ Modifie le programme pour compter par `2` au lieu de `1` à chaque appui sur **A**.

> ❓ Que dois-tu changer dans ton programme ?

**Défi avancé :**

➡️ Affiche l'icône d'un trophée 🏆 lorsque `compteur` atteint `10`.

➡️ Utilise le bloc ``||basic:montrer LEDs||`` après le bloc ``||basic:afficher nombre||`` dans la séquence du bouton A.
```blocks
input.onButtonPressed(Button.A, function () {
    compteur += 1
    basic.showNumber(compteur)
    if (compteur == 10) {
        basic.showIcon(IconNames.Yes)
        basic.pause(1000)
    }
})
```

> ❓ Que se passe-t-il si tu continues d'appuyer sur **A** après avoir atteint `10` ?

🚀 Bravo ! Tu sais maintenant utiliser une variable pour stocker et modifier une valeur !