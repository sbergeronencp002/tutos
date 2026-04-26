# Tutoriel 9 — La minuterie

## @showdialog

🎯 **Objectif** : crée une minuterie qui compte à rebours de 10 à 0 sur le micro:bit !

Dans ce tutoriel, tu vas découvrir comment utiliser une boucle pour faire diminuer une variable automatiquement.

C'est parti ! 🚀

## Étape 1 — Préparer l'espace de travail

🧹 Fais le ménage !

➡️ Supprime le bloc ``||basic:toujours||``.

> 💡 On garde le bloc ``||basic:au démarrage||`` — on va s'en servir à l'étape suivante !

## Étape 2 — Créer une variable

✨ Crée une variable !

➡️ Clique sur **Variables** dans le menu, puis sur **Créer une variable**.

➡️ Nomme-la `temps`.

➡️ Glisse le bloc ``||variables:définir temps à 0||`` à l'intérieur du bloc ``||basic:au démarrage||``.

➡️ Remplace le `0` par `10`.

> 💡 La variable `temps` représente le nombre de secondes restantes. Elle commence à `10` et descendra jusqu'à `0` !

```blocks
let temps = 10
```

## Étape 3 — Démarrer la minuterie

✨ Ajoute une séquence !

➡️ Glisse le bloc ``||input:lorsque le bouton A est pressé||`` dans l'espace de travail.

➡️ Glisse le bloc ``||basic:afficher nombre||`` à l'intérieur.

➡️ Dans le bloc ``||basic:afficher nombre||``, insère la variable `temps`.

> 💡 En appuyant sur **A**, le micro:bit affiche d'abord la valeur de départ avant de commencer le compte à rebours !

```blocks
let temps = 10
input.onButtonPressed(Button.A, function () {
    basic.showNumber(temps)
})
```

## Étape 4 — Ajouter une boucle

✨ Intègre une boucle !

➡️ Glisse le bloc ``||loops:répéter 4 fois||`` sous le bloc ``||basic:afficher nombre||``.

➡️ Remplace la valeur `4` par `10`.

> 💡 La boucle va se répéter **10 fois** — une fois par seconde du compte à rebours !

```blocks
let temps = 10
input.onButtonPressed(Button.A, function () {
    basic.showNumber(temps)
    for (let index = 0; index < 10; index++) {
    	
    }
})
```

## Étape 5 — Faire diminuer le temps

✨ Remplis la boucle !

➡️ À l'intérieur de la boucle, glisse le bloc ``||basic:pause (ms) 100||``.

➡️ Remplace la valeur `100` par `1000`.

➡️ Glisse ensuite le bloc ``||variables:modifier temps de 1||``.

➡️ Remplace la valeur `1` par `-1`.

➡️ Glisse enfin le bloc ``||basic:afficher nombre||`` avec la variable `temps`.

> 💡 À chaque tour de boucle : le micro:bit attend **1 seconde**, retire `1` à `temps`, puis affiche la nouvelle valeur. C'est le compte à rebours !

```blocks
let temps = 10
input.onButtonPressed(Button.A, function () {
    basic.showNumber(temps)
    for (let index = 0; index < 10; index++) {
        basic.pause(1000)
        temps += -1
        basic.showNumber(temps)
    }
})
```

## Étape 6 — Ajouter une alarme

🔔 Signale la fin du compte à rebours !

➡️ Sous la boucle, glisse le bloc ``||basic:montrer l'icône||`` et choisis l'icône de ton choix.

➡️ Glisse ensuite le bloc ``||basic:afficher texte||`` et écris `"Termine!"`.

> 💡 Quand la boucle se termine, le micro:bit sait que le temps est écoulé — il affiche une icône et un message pour signaler la fin !

```blocks
let temps = 10
input.onButtonPressed(Button.A, function () {
    basic.showNumber(temps)
    for (let index = 0; index < 10; index++) {
        basic.pause(1000)
        temps += -1
        basic.showNumber(temps)
    }
    basic.showIcon(IconNames.Yes)
    basic.showString("Termine !")
})
```

## Étape 7 — Réinitialiser avec le bouton B

🔄 Ajoute un bouton de remise à zéro !

➡️ Glisse le bloc ``||variables:définir temps à 0||`` à l'intérieur du bloc ``||input:lorsque le bouton B est pressé||``.

➡️ Remplace le `0` par `10`.

➡️ Glisse ensuite le bloc ``||basic:afficher nombre||`` avec la variable `temps`.

> 💡 Le bouton **B** remet la minuterie à `10` pour recommencer — utile si tu veux relancer le compte à rebours sans redémarrer le micro:bit !

```blocks
let temps = 10
input.onButtonPressed(Button.B, function () {
    temps = 10
    basic.showNumber(temps)
})
```

## Étape 8 — Vérifier sur le simulateur

🖥️ Observe le résultat avant de télécharger !

➡️ Vérifie que ton programme fonctionne correctement sur le **simulateur**.

➡️ Teste les boutons **A** et **B** sur le **simulateur**.

> ❓ Est-ce que le compte à rebours fonctionne bien ? Modifie les blocs au besoin.

## Étape 9 — Télécharger et tester

💾 Envoie ton programme sur le micro:bit !

➡️ Clique sur le bouton **Télécharger** pour transférer ton programme.

➡️ Appuie sur **A** pour démarrer et sur **B** pour réinitialiser !

## Étape 10 — Question réflexive 🤔

❓ **Que se passe-t-il si tu appuies sur A une deuxième fois pendant que le compte à rebours est en cours ?**

❓ **Que se passe-t-il si tu appuies sur B pendant le compte à rebours ?**

> 💡 Le micro:bit ne peut exécuter qu'une séquence à la fois. Si tu appuies sur un bouton pendant qu'une boucle est en cours, il devra attendre que la boucle se termine avant de réagir !

## Étape 11 — Défi de base 🧠

➡️ Modifie la minuterie pour qu'elle compte à rebours de `20` secondes au lieu de `10`.

> ❓ Quels éléments de ton programme dois-tu modifier ?

## Étape 12 — Défi avancé 🧠

➡️ Ajoute une condition pour afficher une icône d'avertissement quand il reste `3` secondes ou moins.

➡️ Glisse un bloc ``||logic:si vrai alors||`` à l'intérieur de la boucle, après le bloc ``||basic:afficher nombre||``.

➡️ Dans la case de la condition, glisse le bloc de comparaison ``||logic:0 ≤ 0||``.

➡️ Dans la partie gauche, insère la variable `temps`. Dans la partie droite, écris `3`.

➡️ À l'intérieur de la condition, glisse le bloc ``||basic:montrer l'icône||`` et choisis l'icône d'avertissement.

```blocks
let temps = 10
input.onButtonPressed(Button.A, function () {
    basic.showNumber(temps)
    for (let index = 0; index < 10; index++) {
        basic.pause(1000)
        temps += -1
        basic.showNumber(temps)
        if (temps <= 3) {
            basic.showIcon(IconNames.Warning)
            basic.pause(300)
        }
    }
    basic.showIcon(IconNames.Yes)
    basic.showString("Termine !")
})
```

> ❓ Que se passe-t-il si tu changes la valeur `3` par `5` ? Et par `1` ?

🚀 Bravo ! Tu sais maintenant utiliser une boucle pour créer un compte à rebours avec le micro:bit !