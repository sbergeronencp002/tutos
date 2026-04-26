# Tutoriel 11 — La radio 📡

## @showdialog

🎯 **Objectif** : envoie des messages secrets à un autre micro:bit par radio !

Dans ce tutoriel, tu vas découvrir les blocs **radio** pour envoyer et recevoir des messages texte sans fil entre deux micro:bits. Tu travailleras en équipe de deux !

C'est parti ! 🚀

## Étape 1 — Préparer l'espace de travail

🧹 Fais le ménage !

➡️ Supprime le bloc ``||basic:toujours||``.

> 💡 On garde le bloc ``||basic:au démarrage||`` — on va s'en servir à l'étape suivante !

## Étape 2 — Choisir un canal radio

✨ Configure la radio !

➡️ Glisse le bloc ``||radio:définir le groupe radio 1||`` à l'intérieur du bloc ``||basic:au démarrage||``.

➡️ Glisse ensuite le bloc ``||basic:montrer LEDs||`` en dessous et reproduis le dessin de l'antenne ci-dessous.

> 💡 Le **canal radio** fonctionne comme une fréquence — deux micro:bits doivent être sur le **même canal** pour se parler !

> ⚠️ En classe, chaque équipe doit choisir un canal **différent** pour éviter de recevoir les messages des autres équipes. Par exemple : équipe 1 → canal `1`, équipe 2 → canal `2`, etc.

```blocks
radio.setGroup(1)
basic.showLeds(`
    . . # . .
    . # . # .
    # . . . #
    . . # . .
    . . # . .
    `)
```

## Étape 3 — Bouton A : envoyer un premier message 💬

✨ Ajoute une première séquence !

➡️ Glisse le bloc ``||radio:envoyer la chaîne " " par radio||`` à l'intérieur du bloc ``||input:lorsque le bouton A est pressé||``.

➡️ Écris `"Bonjour !"` dans le bloc.

➡️ Glisse ensuite le bloc ``||basic:montrer l'icône||`` en dessous et choisis l'icône du crochet ✔️.

> 💡 En appuyant sur **A**, ton micro:bit envoie le texte `"Bonjour !"` directement par radio et affiche un crochet pour confirmer l'envoi !

```blocks
input.onButtonPressed(Button.A, function () {
    radio.sendString("Bonjour !")
    basic.showIcon(IconNames.Yes)
})
```

## Étape 4 — Bouton B : envoyer un deuxième message 💬

✨ Ajoute une deuxième séquence !

➡️ Glisse le bloc ``||radio:envoyer la chaîne " " par radio||`` à l'intérieur du bloc ``||input:lorsque le bouton B est pressé||``.

➡️ Écris `"Au revoir !"` dans le bloc.

➡️ Glisse ensuite le bloc ``||basic:montrer l'icône||`` en dessous et choisis l'icône du crochet ✔️.

> 💡 En appuyant sur **B**, ton micro:bit envoie un message différent et affiche un crochet pour confirmer l'envoi !

```blocks
input.onButtonPressed(Button.B, function () {
    radio.sendString("Au revoir !")
    basic.showIcon(IconNames.Yes)
})
```

## Étape 5 — Recevoir un message

✨ Nouvelle notion : la **réception radio** !

➡️ Glisse le bloc ``||radio:quand une chaîne est reçue receivedString||`` dans l'espace de travail.

➡️ Glisse le bloc ``||basic:afficher texte||`` à l'intérieur.

➡️ Dans le bloc ``||basic:afficher texte||``, insère la variable `receivedString`.

➡️ Glisse ensuite un bloc ``||basic:pause (ms) 100||`` en dessous et remplace la valeur par `3000`.

➡️ Glisse enfin le bloc ``||basic:effacer l'écran||`` sous la pause.

> 💡 Ce bloc se déclenche automatiquement à la réception d'un message. La variable `receivedString` contient le texte reçu et l'affiche tel quel — le message s'affiche pendant **3 secondes**, puis l'écran s'efface !

```blocks
radio.onReceivedString(function (receivedString) {
    basic.showString(receivedString)
    basic.pause(3000)
    basic.clearScreen()
})
```

## Étape 6 — Vérifier sur le simulateur

🖥️ Observe le résultat avant de télécharger !

➡️ Vérifie que ton programme fonctionne correctement sur le **simulateur**.

➡️ Le simulateur affiche deux micro:bits côte à côte — tu peux tester l'envoi et la réception sans avoir besoin d'un deuxième appareil !

> ❓ Est-ce que les messages s'affichent bien sur le deuxième micro:bit ? Modifie les blocs au besoin.

## Étape 7 — Télécharger et tester

💾 Envoie ton programme sur le micro:bit !

➡️ Assure-toi que ton coéquipier a **le même programme** et **le même canal radio** que toi.

➡️ Clique sur le bouton **Télécharger** pour transférer ton programme.

➡️ Appuie sur **A** ou **B** et observe le micro:bit de ton coéquipier !

## Étape 8 — Question réflexive 🤔

❓ **Quelle est la différence entre envoyer un texte et envoyer un nombre par radio ?**

❓ **Que se passe-t-il si les deux coéquipiers appuient sur un bouton en même temps ?**

> 💡 Envoyer un texte est plus simple — le message s'affiche tel quel sans avoir besoin de conditions ! Envoyer un nombre est plus flexible — on peut décider quoi afficher selon le nombre reçu, comme tu l'as vu dans les tutoriels précédents.

## Étape 9 — Défi de base 🧠

➡️ Remplace `"Bonjour !"` et `"Au revoir !"` par tes propres messages secrets avec ton coéquipier.

> ❓ Est-ce que ton coéquipier peut deviner ce que tu voulais lui dire ?

## Étape 10 — Défi avancé 🧠

➡️ Ajoute un troisième message avec le bouton **A+B**.

> ❓ Quels blocs dois-tu ajouter dans ton programme ?

🚀 Bravo ! Tu sais maintenant envoyer et recevoir des messages par radio entre deux micro:bits !