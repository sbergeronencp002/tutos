# Tutoriel 1 — Afficher mon prénom

## @showdialog

🎯 **Objectif** : fais défiler ton prénom en boucle sur l'écran du micro:bit !

Dans ce tutoriel, tu vas apprendre à utiliser le bloc **afficher texte** pour personnaliser l'affichage de ton micro:bit.

C'est parti ! 🚀

## Étape 1 — Préparer l'espace de travail

🧹 Fais le ménage !

➡️ Supprime le bloc ``||basic:au démarrage||``.

> 💡 On garde le bloc ``||basic:toujours||`` — on va s'en servir à l'étape suivante !

## Étape 2 — Le bloc démarrage et le bloc toujours

> 💡 Le micro:bit possède deux blocs très importants :

> 🟡 Le bloc ``||basic:au démarrage||`` s'exécute **une seule fois** — juste au moment où le micro:bit s'allume ou redémarre.

> 🔵 Le bloc ``||basic:toujours||`` s'exécute **en boucle indéfiniment** — il ne s'arrête jamais tant que le micro:bit est allumé.

> ❓ Dans ce tutoriel, pourquoi utilise-t-on le bloc ``||basic:toujours||`` plutôt que le bloc ``||basic:au démarrage||`` pour afficher le prénom ?

> 💡 Parce qu'on veut que le prénom défile **en continu** — si on utilisait ``||basic:au démarrage||``, il ne s'afficherait qu'une seule fois au démarrage, puis disparaîtrait !

## Étape 3 — Ajouter un bloc

✨ Ajoute un bloc !

➡️ Glisse le bloc ``||basic:afficher texte||`` à l'intérieur du bloc ``||basic:toujours||``.

```blocks
basic.forever(function () {
    basic.showString("Hello!")
})
```

## Étape 4 — Écrire mon prénom

✏️ Remplace le texte par défaut !

➡️ Efface le mot ``Hello!`` dans le bloc ``||basic:afficher texte||``.

➡️ Écris ton prénom à la place (ex. : `Seb`).

```blocks
basic.forever(function () {
    basic.showString("Seb")
})
```

## Étape 5 — Tester les caractères spéciaux

🔬 Fais une petite expérience !

➡️ Écris ton prénom **avec** au moins un caractère spécial : `à â ä é è ï ù`

➡️ Observe le résultat sur le **simulateur**.

> ❓ Que remarques-tu ? L'affichage est-il correct ?

```blocks
basic.forever(function () {
    basic.showString("Séb")
})
```

## Étape 6 — Corriger l'affichage

✅ Reviens à un affichage correct !

➡️ Réécris ton prénom **sans** caractères spéciaux ni accents.

➡️ Vérifie sur le **simulateur** que ton prénom s'affiche bien.

```blocks
basic.forever(function () {
    basic.showString("Seb")
})
```

## Étape 7 — Vérifier sur le simulateur

🖥️ Observe le résultat avant de télécharger !

➡️ Vérifie que ton prénom s'affiche correctement sur le **simulateur**.

> ❓ Est-ce bien le résultat attendu ? Modifie les blocs au besoin.

## Étape 8 — Télécharger le programme

💾 Envoie ton programme sur le micro:bit !

➡️ Clique sur le bouton **Télécharger** pour transférer ton programme.

## Étape 9 — Observer le résultat

👀 Regarde ton micro:bit !

➡️ Observe ton prénom défiler sur l'écran de ton micro:bit.

> 🎉 Si tout fonctionne bien, félicitations ! Tu viens de créer ton premier programme personnalisé.

## Étape 10 — Défi supplémentaire 🧠

**Défi de base**

➡️ Ajoute un deuxième bloc ``||basic:afficher texte||`` pour faire défiler ton **nom de famille** après ton prénom.

➡️ Ajoute un bloc ``||basic:pause (ms)||`` entre les deux blocs et remplace la valeur par `1000`.

> ❓ Que se passe-t-il si tu changes la valeur de la pause à `100` ? Et à `3000` ?

```blocks
basic.forever(function () {
    basic.showString("Seb")
    basic.pause(1000)
    basic.showString("Bergeron")
    basic.pause(1000)
})
```

## Étape 10 — Défi supplémentaire 🧠


**Défi avancé**

➡️ Ajoute un bloc ``||basic:afficher nombre||`` pour afficher ton année de naissance après ton prénom.

```blocks
basic.forever(function () {
    basic.showString("Seb")
    basic.showNumber(1986)
})
```

> ❓ Que se passe-t-il si tu mets un nombre négatif ?

🚀 Bravo ! Tu maîtrises maintenant l'affichage de texte sur le micro:bit !