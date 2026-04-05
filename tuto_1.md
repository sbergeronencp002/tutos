# Tutoriel 1 — Afficher mon prénom

## @showdialog

🎯 **Objectif** : fais défiler ton prénom en boucle sur l'écran du micro:bit !

Dans ce tutoriel, tu vas apprendre à utiliser le bloc **afficher texte** pour personnaliser l'affichage de ton micro:bit.

C'est parti ! 🚀

## Étape 1 — Ajouter un bloc

✨ Ajoute un bloc à ton programme !

➡️ Glisse le bloc ``||basic:afficher texte||`` à l'intérieur du bloc ``||basic:toujours||``.

💡 Le bloc **toujours** répète son contenu en boucle indéfiniment. Ton prénom défilera donc sans arrêt !

```blocks
basic.forever(function () {
    basic.showString("Hello!")
})
```

## Étape 2 — Écrire mon prénom

✏️ Remplace le texte par défaut !

➡️ Efface le mot ``Hello!`` dans le bloc ``||basic:afficher texte||``.

➡️ Écris ton prénom à la place (ex. : `Seb`).

```blocks
basic.forever(function () {
    basic.showString("Seb")
})
```

## @showdialog

⚠️ **Attention aux accents !**

Le micro:bit ne sait pas toujours afficher correctement les lettres accentuées et certains caractères spéciaux.

Il vaut mieux les éviter pour avoir un affichage propre !

## Étape 3 — Tester les caractères spéciaux

🔬 Fais une petite expérience !

➡️ Écris ton prénom **avec** au moins un caractère spécial : `à â ä é è ï ù`

➡️ Observe le résultat sur le **simulateur**.

```blocks
basic.forever(function () {
    basic.showString("Séb")
})
```

## Étape 4 — Corriger l'affichage

✅ Reviens à un affichage correct !

➡️ Réécris ton prénom **sans** caractères spéciaux ni accents.

➡️ Vérifie sur le **simulateur** que ton prénom s'affiche bien.

```blocks
basic.forever(function () {
    basic.showString("Seb")
})
```

## Étape 5 — Télécharger le programme

💾 Envoie ton programme sur le micro:bit !

➡️ Clique sur le bouton **Télécharger** pour transférer ton programme.

## Étape 6 — Observer le résultat

👀 Regarde ton micro:bit !

➡️ Observe ton prénom défiler sur l'écran de ton micro:bit.

> 🎉 Si tout fonctionne bien, félicitations ! Tu viens de créer ton premier programme personnalisé.

## Étape 7 — Défi supplémentaire 🧠

Tu veux aller plus loin ?

➡️ Ajoute un deuxième bloc ``||basic:afficher texte||`` pour faire défiler aussi ton **nom de famille** après ton prénom.

> 💡 Les deux blocs s'exécuteront l'un après l'autre, en boucle.
```blocks
basic.forever(function () {
    basic.showString("Seb")
    basic.showString("Bergeron")
})
```

🚀 Bravo, tu maîtrises maintenant l'affichage de texte sur le micro:bit !