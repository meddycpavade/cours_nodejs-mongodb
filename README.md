# cours_nodejs-mongodb
`****************** Commencer un projet ******************`
Pour démarrer n'importe quel projet nodejs, il faut tout d'abord générer un package.json. C'est un petit fichier qui contient toutes les inos de notre projet.

Pour créer ce package.json il faut utiliser la commande :

> `npm init`
Important : Il faut lancer cette commande uniquement au tout début du projet et dans un dossier vide de votre choix

`**************************************************************`

`****************** Installer et configurer typescript  ******************`
Pour pouvoir faire du typescript, il faut tout d'abord l'installer et le configurer sur notre projet. Pour cela demandons tout d'abord à installer typescript :

# Install typescript ainsi que les types pour nodejs
> `npm i -D typescript @types/node`

`
La petite option -D veut dire "développement". Il faut savoir que nous pouvons installer des librairies pour la production (des librairies qui seront utilisé sur le serveur final) et des librairies de développement (utilisable uniquement sur notre machine). Ici c'est la cas de typescript.

Attention le dossier node_modules ne doit pas être versionné sur git !
`
`**************************************************************`

`****************** Installer et tsnode  ******************`

Il permet d'éxécuter directement du typescript comme du javascript (sans passer par l'étape de compilation).

Installer ts-node :

> `npm i -D ts-node`

!Attention : TSNODE est très très très gourmand en mémoire vive. Il ne doit surtout être utilisé sur le serveur de production.

`**************************************************************`

`****************** Configuration de typescript pour compiler tout un projet  ******************`


Pour cela on vas utiliser le fichier tsconfig.json. Dans ce fichier nous retrouvons des options nous permettant de définir comment un projet typescript doit se compiler en javascript.

Pour cela il faut, dans le fihier tsconfig.json décommenté et configurer les options suivantes :

"rootDir" : Correspond au dossier contenant tout nos fichier typescript. Ce dossier c'est toujours src.
"outDir" : Correspond au dossier qui contiendra les fichier javascript compilé par typescript.

! Attention le dossier outDir (généralement dist) ne doit pas être versionné sur git !

Il suffit de lancer la commande suivante afin de compiler tout nos fichier typescript en javascript.

> `npx tsc`


`**************************************************************`

`****************** Créer ses propres commande npm !  ******************`


Pour cela nous pouvons créer des commande npm depuis notre package.json. Pour cela il faut se rendre dans le section scripts du fichier package.json pour pouvoir créer nos propre commande :

{
  //....
  "scripts": {
    "init:typescript": "tsc --init"
  }
}

Maintenant pour lancer notre commande npm, rien de plus simple :

> `npm run init:typescript`

`Il éxiste 3 commandes fournie de base par npm : "start", "test" et "build". Ces 3 commandes sont obligatoire pour tout projet nodejs. La commande "start" démarre l'application, la commande "test" test l'application la commande "build" construit l'application. Pour ces 3 commande pas besoin de spécifier run juste après npm.`