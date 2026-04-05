# Tutoriel 1

## @showdialog

🎯 **Objectif** 🎯 : fais défiler ton prénom en boucle sur l'écran du micro:bit ! 

C'est parti ! 🚀 🚀 🚀

## Étape 1

✨ Ajoute un bloc !

➡️ Ajoute le bloc ``|| basic: afficher texte ||`` dans le bloc ``||basic: toujours||``.

```blocks

basic.forever(function () {
    basic.showString("Hello!")
})

```

## Étape 2

✏️ Modifie les valeurs !

➡️ Efface le mot ``|| basic: Hello! ||`` du bloc ``|| basic: afficher texte ||``.

➡️ Écris ton prénom dans le bloc ``|| basic: afficher texte ||`` (ex. : Seb). 

```blocks

basic.forever(function () {
    basic.showString("Seb") 
})

```

## @showdialog

🚨🚨 **Attention !** 🚨🚨

Il vaut mieux éviter les accents et certains caractères spéciaux.

## Étape 3

✏️ Modifie les valeurs !

➡️ Écris ton prénom avec au moins un caractère spécial. 

➡️ ** à â ä é è ï ù **

➡️ Observe ton prénom défiler **sur le simulateur**. 

```blocks

basic.forever(function () {
    basic.showString("Seb") 
})

```

## Étape 4

➡️ Écris correctement ton prénom sans caractères spéciaux.

🖥️ Est-ce que ton prénom s'affiche correctement sur le simulateur ?

💾 Télécharge la programmation.

## Étape 5

➡️ Observe ton prénom défiler fièrement sur l'écran du micro:bit. 

## Étape 6

🧠 **Défi supplémentaire**. 🧠

➡️ Fais défiler également ton nom de famille en ajoutant un bloc ``|| basic: Hello! ||``.

Prêt ? C'est parti ! 🚀 🚀 🚀

```blocks

basic.forever(function () {
    basic.showString("Seb")
    basic.showString("Bergeron")  
})

```