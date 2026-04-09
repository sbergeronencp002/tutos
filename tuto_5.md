# Tutoriel 5 — Animer un battement de cœur

## @showdialog

🎯 **Objectif** : fais battre le cœur de ton micro:bit lorsque tu le secoues !

Dans ce tutoriel, tu vas combiner des icônes, des pauses et une **boucle** pour créer une animation fluide.

C'est parti ! 🚀

## Étape 1 — Préparer l'espace de travail

🧹 Fais du ménage !

➡️ Supprime les blocs ``||basic:au démarrage||`` et ``||basic:toujours||``.

> 💡 Comme au tutoriel précédent, ton programme va **attendre un événement** avant de faire quoi que ce soit — cette fois, ce sera une secousse !

## Étape 2 — Grand cœur ❤️

✨ Ajoute un premier bloc !

➡️ Glisse le bloc ``||basic:montrer l'icône||`` à l'intérieur du bloc ``||input:lorsque secouer||``.

➡️ Choisis l'icône du **grand cœur**.

```blocks
input.onGesture(Gesture.Shake, function () {
    basic.showIcon(IconNames.Heart)
})
```

## Étape 3 — Ajouter une pause ⏱️

➡️ Glisse le bloc ``||basic:pause (ms) 100||`` sous le bloc ``||basic:montrer l'icône||``.

> 💡 Sans pause, l'animation irait trop vite pour être visible !

```blocks
input.onGesture(Gesture.Shake, function () {
    basic.showIcon(IconNames.Heart)
    basic.pause(100)
})
```

## Étape 4 — Petit cœur 🤍

✨ Ajoute un deuxième bloc !

➡️ Glisse un nouveau bloc ``||basic:montrer l'icône||`` sous la pause.

➡️ Choisis l'icône du **petit cœur**.

```blocks
input.onGesture(Gesture.Shake, function () {
    basic.showIcon(IconNames.Heart)
    basic.pause(100)
    basic.showIcon(IconNames.SmallHeart)
})
```

## Étape 5 — Ajouter une deuxième pause ⏱️

➡️ Glisse un autre bloc ``||basic:pause (ms) 100||`` sous le petit cœur.

> 💡 On ajoute une pause après chaque icône pour que le rythme soit régulier — comme un vrai battement de cœur !

```blocks
input.onGesture(Gesture.Shake, function () {
    basic.showIcon(IconNames.Heart)
    basic.pause(100)
    basic.showIcon(IconNames.SmallHeart)
    basic.pause(100)
})
```

## Étape 6 — Répéter avec une boucle 🔁

✨ Nouvelle notion : la **boucle** !

➡️ Glisse le bloc ``||loops:Répéter 4 fois||`` autour de tes quatre blocs.

➡️ Remplace la valeur `4` par `10`.

> 💡 Une boucle répète automatiquement les blocs qu'elle contient. Ici, le cœur battra **10 fois** à chaque secousse — sans que tu aies à copier tes blocs 10 fois !

```blocks
input.onGesture(Gesture.Shake, function () {
    for (let index = 0; index < 10; index++) {
        basic.showIcon(IconNames.Heart)
        basic.pause(100)
        basic.showIcon(IconNames.SmallHeart)
        basic.pause(100)
    }
})
```
## Étape 7 — Vérifier sur le simulateur

🖥️ Observe le résultat avant de télécharger !

➡️ Vérifie que ton animation s'affiche correctement sur le **simulateur**.

➡️ Teste la secousse sur le **simulateur** en cliquant sur le bouton **SHAKE** !

> ❓ Est-ce bien le comportement attendu ? Modifie les blocs au besoin.

## Étape 8 — Télécharger et tester

💾 Envoie ton programme sur le micro:bit !

➡️ Clique sur le bouton **Télécharger** pour transférer ton programme.

➡️ Secoue ton micro:bit et observe l'animation !

## Étape 9 — Question réflexive 🤔

❓ **Pourquoi rien ne s'affiche sur le micro:bit au démarrage ?**

❓ **Quelle action dois-tu réaliser pour déclencher l'animation ?**

> 💡 Tu peux aussi tester la secousse sur le **simulateur** en cliquant sur le bouton **SHAKE** !

## Étape 10 — Défi supplémentaire 🧠

Tu veux aller plus loin ?

**Défi de base :**

➡️ Modifie la valeur des pauses pour accélérer ou ralentir le battement de cœur.

➡️ Modifie le nombre de répétitions de la boucle.

> ❓ Quelle combinaison donne l'animation la plus réaliste ?

## Étape 10 — Défi supplémentaire 🧠

**Défi avancé :**

➡️ Ajoute un bloc ``||basic:effacer l'écran||`` et une pause à la fin de la boucle pour ajouter un moment de silence entre chaque battement.

> ❓ Que se passe-t-il si tu mets la pause très longue, comme `2000` ? Et très courte, comme `50` ?

```blocks
input.onGesture(Gesture.Shake, function () {
    for (let index = 0; index < 10; index++) {
        basic.showIcon(IconNames.Heart)
        basic.pause(100)
        basic.showIcon(IconNames.SmallHeart)
        basic.pause(100)
    }
    basic.clearScreen()
    basic.pause(500)
})
```