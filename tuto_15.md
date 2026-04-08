# Tutoriel 15 — Le coffre-fort 🔒

## @showdialog

🎯 **Objectif** : transforme le micro:bit en coffre-fort numérique avec une combinaison secrète de 4 lettres !

Dans ce tutoriel, tu vas utiliser des blocs **Texte** pour mémoriser et vérifier une combinaison secrète — l'ordre des boutons est important !

C'est parti ! 🚀

## Étape 1 — Préparer l'espace de travail

🧹 Fais le ménage !

➡️ Supprime le bloc ``||basic:toujours||``.

> 💡 On garde le bloc ``||basic:au démarrage||`` — on va s'en servir à l'étape suivante !

## Étape 2 — Créer la variable combinaison

✨ Crée une première variable !

➡️ Clique sur **Variables** dans le menu, puis sur **Créer une variable**.

➡️ Nomme-la `combinaison`.

➡️ Glisse le bloc ``||variables:définir combinaison à " "||`` à l'intérieur du bloc ``||basic:au démarrage||``.

```blocks
let combinaison = ""
```

## Étape 3 — Définir la combinaison secrète

➡️ Remplace la valeur du bloc ``||variables:définir combinaison||`` par le bloc ``||text:" "||`` depuis l'onglet **Texte**.

➡️ Écris `AABB` dans le bloc ``||text:" "||``.

> 💡 La variable `combinaison` contient maintenant ta combinaison secrète — `"AABB"` veut dire : appuie sur **A**, **A**, **B**, **B** dans cet ordre !

```blocks
let combinaison = "AABB"
```

## Étape 4 — Créer la variable entree

✨ Crée une deuxième variable !

➡️ Clique sur **Variables** dans le menu, puis sur **Créer une variable**.

➡️ Nomme-la `entree`.

➡️ Glisse le bloc ``||variables:définir entree à " "||`` sous le bloc ``||variables:définir combinaison||``.

➡️ Laisse la valeur vide.

> 💡 La variable `entree` va mémoriser les boutons que tu appuies — elle commence vide, comme un coffre-fort qui attend sa combinaison !

```blocks
let combinaison = "AABB"
let entree = ""
```

## Étape 5 — Message de démarrage

✨ Ajoute un message de démarrage !

➡️ Glisse le bloc ``||basic:afficher texte||`` sous le bloc ``||variables:définir entree||``.

➡️ Écris `"Pret !"` dans le bloc.

```blocks
let combinaison = "AABB"
let entree = ""
basic.showString("Pret !")
```

## Étape 6 — Bouton A : ajouter la lettre

✨ Ajoute une première séquence !

➡️ Glisse le bloc ``||variables:définir entree à " "||`` à l'intérieur du bloc ``||input:lorsque le bouton A est pressé||``.

➡️ Dans le bloc, insère le bloc ``||text:concaténation||`` depuis l'onglet **Texte**.

➡️ Dans la partie gauche du bloc ``||text:concaténation||``, insère la variable `entree`.

➡️ Dans la partie droite, écris `"A"`.

> 💡 Le bloc **concaténation** colle deux morceaux de texte ensemble — ici, il ajoute `"A"` à la fin de ce qui est déjà dans `entree` !

```blocks
input.onButtonPressed(Button.A, function () {
    entree = entree + "A"
})
```

## Étape 7 — Bouton A : afficher, pause et effacement

➡️ Glisse le bloc ``||basic:afficher texte||`` sous le bloc ``||variables:définir entree||`` et écris `"A"`.

➡️ Glisse le bloc ``||basic:pause (ms) 100||`` en dessous et remplace la valeur par `500`.

➡️ Glisse enfin le bloc ``||basic:effacer l'écran||`` en dessous.

```blocks
input.onButtonPressed(Button.A, function () {
    entree = entree + "A"
    basic.showString("A")
    basic.pause(500)
    basic.clearScreen()
})
```

## Étape 8 — Bouton B : ajouter la lettre

✨ Ajoute une deuxième séquence !

➡️ Glisse le bloc ``||variables:définir entree à " "||`` à l'intérieur du bloc ``||input:lorsque le bouton B est pressé||``.

➡️ Dans le bloc, insère le bloc ``||text:concaténation||`` depuis l'onglet **Texte**.

➡️ Dans la partie gauche du bloc ``||text:concaténation||``, insère la variable `entree`.

➡️ Dans la partie droite, écris `"B"`.

> 💡 Même principe qu'à l'étape précédente — cette fois, la lettre `"B"` est ajoutée à la fin de `entree` !

```blocks
input.onButtonPressed(Button.B, function () {
    entree = entree + "B"
})
```

## Étape 9 — Bouton B : afficher, pause et effacement

➡️ Glisse le bloc ``||basic:afficher texte||`` sous le bloc ``||variables:définir entree||`` et écris `"B"`.

➡️ Glisse le bloc ``||basic:pause (ms) 100||`` en dessous et remplace la valeur par `500`.

➡️ Glisse enfin le bloc ``||basic:effacer l'écran||`` en dessous.

```blocks
input.onButtonPressed(Button.B, function () {
    entree = entree + "B"
    basic.showString("B")
    basic.pause(500)
    basic.clearScreen()
})
```

## Étape 10 — Bouton A+B : préparer la vérification

✨ Ajoute la séquence de vérification !

➡️ Glisse deux blocs ``||logic:si vrai alors||`` à l'intérieur du bloc ``||input:lorsque le bouton A+B est pressé||``.

➡️ Dans chaque condition, glisse le bloc de comparaison ``||logic:0 = 0||``.

> 💡 On va remplir les deux conditions aux étapes suivantes !

## Étape 11 — Condition : bonne combinaison ✅

✨ Remplis la première condition !

➡️ Dans la partie gauche de la première condition, insère la variable `entree`.

➡️ Dans la partie droite, insère la variable `combinaison`.

➡️ À l'intérieur, glisse le bloc ``||basic:afficher texte||`` et écris `"Ouvert !"`.

```blocks
input.onButtonPressed(Button.AB, function () {
    if (entree == combinaison) {
        basic.showString("Ouvert !")
    }
    if (0 == 0) {
    }
})
```

## Étape 12 — Condition : mauvaise combinaison ❌

✨ Remplis la deuxième condition !

➡️ Dans la partie gauche de la deuxième condition, insère la variable `entree`.

➡️ Remplace le symbole `=` par `≠`.

➡️ Dans la partie droite, insère la variable `combinaison`.

➡️ À l'intérieur, glisse le bloc ``||basic:afficher texte||`` et écris `"Erreur !"`.

```blocks
input.onButtonPressed(Button.AB, function () {
    if (entree == combinaison) {
        basic.showString("Ouvert !")
    }
    if (entree != combinaison) {
        basic.showString("Erreur !")
    }
})
```

## Étape 13 — Réinitialiser l'entrée

✨ Réinitialise la variable `entree` !

➡️ Glisse le bloc ``||variables:définir entree à " "||`` **sous** les deux conditions, à la fin de la séquence.

➡️ Laisse la valeur vide.

> 💡 On réinitialise `entree` **après** les deux conditions — peu importe le résultat, le coffre-fort est prêt pour une nouvelle tentative !

```blocks
input.onButtonPressed(Button.AB, function () {
    if (entree == combinaison) {
        basic.showString("Ouvert !")
    }
    if (entree != combinaison) {
        basic.showString("Erreur !")
    }
    entree = ""
})
```

## Étape 14 — Vérifier sur le simulateur

🖥️ Observe le résultat avant de télécharger !

➡️ Vérifie que ton programme fonctionne correctement sur le **simulateur**.

➡️ Teste la combinaison `"AABB"` — appuie sur **A**, **A**, **B**, **B**, puis **A+B**.

➡️ Essaie aussi une mauvaise combinaison !

> ❓ Est-ce que le coffre-fort s'ouvre avec la bonne combinaison ? Modifie les blocs au besoin.

## Étape 15 — Télécharger et tester

💾 Envoie ton programme sur le micro:bit !

➡️ Clique sur le bouton **Télécharger** pour transférer ton programme.

➡️ Teste ta combinaison et fais deviner la combinaison à un ami !

## Étape 16 — Question réflexive 🤔

❓ **Combien de combinaisons différentes sont possibles avec 4 lettres A et B ?**

❓ **Est-ce que `"AABB"` et `"BBAA"` donnent le même résultat ? Pourquoi ?**

> 💡 Avec 4 lettres et 2 choix possibles (A ou B), il y a **16 combinaisons différentes** — l'ordre est crucial, ce qui rend le coffre-fort difficile à deviner !

## Étape 17 — Défi supplémentaire 🧠

**Défi de base :**

➡️ Change la combinaison secrète `"AABB"` pour une combinaison de ton choix.

> ❓ Combien de tentatives faut-il à ton ami pour trouver ta combinaison ?

**Défi avancé :**

➡️ Ajoute un compteur de tentatives — après **3 essais incorrects**, affiche `"Bloque !"` et empêche toute nouvelle tentative jusqu'à ce que le micro:bit soit redémarré.

```blocks
let tentatives = 0
let combinaison = "AABB"
let entree = ""
basic.showString("Pret !")
input.onButtonPressed(Button.A, function () {
    entree = entree + "A"
    basic.showString("A")
    basic.pause(500)
    basic.clearScreen()
})
input.onButtonPressed(Button.B, function () {
    entree = entree + "B"
    basic.showString("B")
    basic.pause(500)
    basic.clearScreen()
})
input.onButtonPressed(Button.AB, function () {
    if (entree == combinaison) {
        basic.showString("Ouvert !")
        tentatives = 0
    }
    if (entree != combinaison) {
        tentatives += 1
        if (tentatives >= 3) {
            basic.showString("Bloque !")
        } else {
            basic.showString("Erreur !")
        }
    }
    entree = ""
})
```

> ❓ Que se passe-t-il si tu redémarres le micro:bit après avoir été bloqué ?

🚀 Bravo ! Tu as créé un vrai coffre-fort numérique — personne ne pourra accéder à tes secrets sans connaître la combinaison dans le bon ordre !