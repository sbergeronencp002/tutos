# Tutoriel 1 — Afficher un mot

## @showdialog

🎯 **Objectif** : fais défiler ton prénom en boucle sur l'écran du micro:bit !

Dans ce tutoriel, tu vas apprendre à utiliser le bloc **afficher texte** pour personnaliser l'affichage de ton micro:bit.

C'est parti ! 🚀

## Étape 1 — Le bloc démarrage et le bloc toujours

> 💡 Le micro:bit possède deux blocs très importants :

> 🟡 Le bloc ``||basic:au démarrage||`` s'exécute **une seule fois** — juste au moment où le micro:bit s'allume ou redémarre.

> 🔵 Le bloc ``||basic:toujours||`` s'exécute **en boucle indéfiniment** — il ne s'arrête jamais tant que le micro:bit est allumé.

> ❓ Dans ce tutoriel, pourquoi utilise-t-on le bloc ``||basic:toujours||`` plutôt que le bloc ``||basic:au démarrage||`` pour afficher le prénom ?

> 💡 Parce qu'on veut que le prénom défile **en continu** — si on utilisait ``||basic:au démarrage||``, il ne s'afficherait qu'une seule fois au démarrage, puis disparaîtrait !

## Étape 2 — Ajouter un bloc

✨ Ajoute un bloc !

➡️ Glisse le bloc ``||basic:afficher texte||`` à l'intérieur du bloc ``||basic:toujours||``.

```blocks
basic.forever(function () {
    basic.showString("Hello!")
})
```

## Étape 3 — Écrire mon prénom

✏️ Remplace le texte par défaut !

➡️ Efface le mot ``Hello!`` dans le bloc ``||basic:afficher texte||``.

➡️ Écris ton prénom à la place (ex. : `Seb`).

```blocks
basic.forever(function () {
    basic.showString("Seb")
})
```

## Étape 4 — Tester les caractères spéciaux

🔬 Fais une petite expérience !

➡️ Écris ton prénom **avec** au moins un caractère spécial : `à â ä é è ï ù`

➡️ Observe le résultat sur le **simulateur**.

> ❓ Que remarques-tu ? L'affichage est-il correct ?

```blocks
basic.forever(function () {
    basic.showString("Séb")
})
```

## Étape 5 — Corriger l'affichage

✅ Reviens à un affichage correct !

➡️ Réécris ton prénom **sans** caractères spéciaux ni accents.

➡️ Vérifie sur le **simulateur** que ton prénom s'affiche bien.

```blocks
basic.forever(function () {
    basic.showString("Seb")
})
```

## Étape 6 — Vérifier sur le simulateur

🖥️ Observe le résultat avant de télécharger !

➡️ Vérifie que ton prénom s'affiche correctement sur le **simulateur**.

> ❓ Est-ce bien le résultat attendu ? Modifie les blocs au besoin.

## Étape 7 — Télécharger le programme

💾 Envoie ton programme sur le micro:bit !

➡️ Clique sur le bouton **Télécharger** pour transférer ton programme.

## Étape 8 — Observer le résultat

👀 Regarde ton micro:bit !

➡️ Observe ton prénom défiler sur l'écran de ton micro:bit.

> 🎉 Si tout fonctionne bien, félicitations ! Tu viens de créer ton premier programme personnalisé.

## Étape 9 — Défi supplémentaire 🧠

**Défi de base :**

➡️ Utilise le bloc ``||basic:au démarrage||`` pour afficher ton **nom de famille** une seule fois au démarrage.

➡️ Ajoute un bloc ``||basic:effacer l'écran||`` après le bloc ``||basic:afficher texte||``.

➡️ Garde ton **prénom** dans le bloc ``||basic:toujours||``.

```blocks
basic.showString("Bergeron")
basic.clearScreen()
basic.forever(function () {
    basic.showString("Seb")
})
```

> ❓ Que se passe-t-il au démarrage ? Et ensuite ? Vois-tu la différence entre les deux blocs ?

**Défi avancé :**

➡️ Utilise le bloc ``||basic:au démarrage||`` pour afficher ton **nom de famille**.

➡️ Dans le bloc ``||basic:toujours||``, alterne entre ton **prénom** et ton **année de naissance** avec une pause entre les deux.

```blocks
basic.showString("Bergeron")
basic.clearScreen()
basic.forever(function () {
    basic.showString("Seb")
    basic.pause(1000)
    basic.showNumber(1986)
    basic.pause(1000)
})
```

> ❓ Combien de fois le nom de famille s'affiche-t-il ? Et le prénom ? Pourquoi cette différence ?

🚀 Bravo ! Tu maîtrises maintenant la différence entre le bloc ``||basic:au démarrage||`` et le bloc ``||basic:toujours||`` !