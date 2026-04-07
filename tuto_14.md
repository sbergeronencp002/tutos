# Tutoriel 14 — L'accéléromètre 📐

## @showdialog

🎯 **Objectif** : fais afficher une flèche selon l'inclinaison de ton micro:bit !

Dans ce tutoriel, tu vas découvrir l'**accéléromètre** du micro:bit — il peut détecter dans quelle direction tu l'inclines, sans aucune valeur numérique à mémoriser !

C'est parti ! 🚀

## Étape 1 — Préparer l'espace de travail

🧹 Fais le ménage !

➡️ Supprime les blocs ``||basic:au démarrage||`` et ``||basic:toujours||``.

> 💡 Comme pour les boutons et la secousse, le micro:bit va **attendre** que tu l'inclines avant de réagir !

## Étape 2 — Logo vers le haut ⬆️

✨ Ajoute une première séquence !

➡️ Glisse le bloc ``||input:lorsque logo vers le haut||`` dans l'espace de travail.

➡️ Glisse le bloc ``||basic:montrer l'icône||`` à l'intérieur et choisis la flèche vers le haut ⬆️.

> 💡 Quand le logo du micro:bit pointe vers le **haut**, le micro:bit affiche une flèche vers le haut !

```blocks
input.onGesture(Gesture.ScreenUp, function () {
    basic.showIcon(IconNames.ArrowNorth)
})
```

## Étape 3 — Logo vers le bas ⬇️

✨ Ajoute une deuxième séquence !

➡️ Glisse le bloc ``||input:lorsque logo vers le bas||`` dans l'espace de travail.

➡️ Glisse le bloc ``||basic:montrer l'icône||`` à l'intérieur et choisis la flèche vers le bas ⬇️.

> 💡 Quand le logo pointe vers le **bas**, le micro:bit affiche une flèche vers le bas !

```blocks
input.onGesture(Gesture.ScreenDown, function () {
    basic.showIcon(IconNames.ArrowSouth)
})
```

## Étape 4 — Incliné à gauche ⬅️

✨ Ajoute une troisième séquence !

➡️ Glisse le bloc ``||input:lorsque incliné à gauche||`` dans l'espace de travail.

➡️ Glisse le bloc ``||basic:montrer l'icône||`` à l'intérieur et choisis la flèche vers la gauche ⬅️.

```blocks
input.onGesture(Gesture.TiltLeft, function () {
    basic.showIcon(IconNames.ArrowWest)
})
```

## Étape 5 — Incliné à droite ➡️

✨ Ajoute une quatrième séquence !

➡️ Glisse le bloc ``||input:lorsque incliné à droite||`` dans l'espace de travail.

➡️ Glisse le bloc ``||basic:montrer l'icône||`` à l'intérieur et choisis la flèche vers la droite ➡️.

```blocks
input.onGesture(Gesture.TiltRight, function () {
    basic.showIcon(IconNames.ArrowEast)
})
```

## Étape 6 — Face vers le haut 😊

✨ Ajoute une cinquième séquence !

➡️ Glisse le bloc ``||input:lorsque face vers le haut||`` dans l'espace de travail.

➡️ Glisse le bloc ``||basic:montrer l'icône||`` à l'intérieur et choisis le visage heureux 😊.

> 💡 Quand le micro:bit est posé **à plat**, il affiche un visage heureux — il est dans sa position de repos !

```blocks
input.onGesture(Gesture.FaceUp, function () {
    basic.showIcon(IconNames.Happy)
})
```

## Étape 7 — Vérifier sur le simulateur

🖥️ Observe le résultat avant de télécharger !

➡️ Vérifie que ton programme fonctionne correctement sur le **simulateur**.

➡️ Clique sur les différentes orientations du simulateur et observe les flèches changer.

> ❓ Est-ce que les flèches s'affichent bien selon l'inclinaison ? Modifie les blocs au besoin.

## Étape 8 — Télécharger et tester

💾 Envoie ton programme sur le micro:bit !

➡️ Clique sur le bouton **Télécharger** pour transférer ton programme.

➡️ Incline ton micro:bit dans toutes les directions et observe l'écran !

## Étape 9 — Question réflexive 🤔

❓ **Quelle est la différence entre ce tutoriel et les tutoriels sur les boutons et la secousse ?**

❓ **Que se passe-t-il si tu inclines le micro:bit en diagonale ?**

> 💡 C'est le même principe — le micro:bit **attend un événement** avant de réagir. La seule différence, c'est que l'événement est une inclinaison plutôt qu'un appui sur un bouton !

## Étape 10 — Défi supplémentaire 🧠

**Défi de base :**

➡️ Remplace les flèches par des dessins de ton choix avec le bloc ``||basic:montrer LEDs||``.

> ❓ Peux-tu dessiner une main qui pointe dans chaque direction ?

**Défi avancé :**

➡️ Ajoute une séquence pour l'événement ``||input:lorsque face vers le bas||`` — affiche un visage triste 😞 quand le micro:bit est retourné face vers le bas.

➡️ Ajoute aussi un bloc ``||basic:afficher texte||`` pour afficher le nom de la direction après chaque flèche.

```blocks
input.onGesture(Gesture.FaceDown, function () {
    basic.showIcon(IconNames.Sad)
    basic.showString("Bas")
})
input.onGesture(Gesture.FaceUp, function () {
    basic.showIcon(IconNames.Happy)
    basic.showString("Plat")
})
input.onGesture(Gesture.TiltLeft, function () {
    basic.showIcon(IconNames.ArrowWest)
    basic.showString("Gauche")
})
input.onGesture(Gesture.TiltRight, function () {
    basic.showIcon(IconNames.ArrowEast)
    basic.showString("Droite")
})
input.onGesture(Gesture.ScreenUp, function () {
    basic.showIcon(IconNames.ArrowNorth)
    basic.showString("Haut")
})
input.onGesture(Gesture.ScreenDown, function () {
    basic.showIcon(IconNames.ArrowSouth)
    basic.showString("Bas")
})
```

> ❓ Peux-tu deviner l'orientation du micro:bit en lisant seulement le texte affiché, sans regarder les flèches ?

🚀 Bravo ! Tu sais maintenant utiliser l'accéléromètre pour détecter l'inclinaison de ton micro:bit dans toutes les directions !