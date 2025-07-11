# 📚 L'essentiel de git
## 📜 Sommaire
- [Vocabulaire de base](#vocabulaire-de-base)
- [Les commandes à maitriser absolument](#les-commandes-à-maitriser-absolument)
  - [1. Cloner un repository](#1-cloner-un-repository)
  - [2. Ajouter du contenu](#2-ajouter-du-contenu)
  - [3. Mettre à jour l'historique](#3-mettre-à-jour-lhistorique)
  - [4. Mettre en ligne les modifications](#4-mettre-en-ligne-les-modifications)
  - [5. Status](#5-status)
- [Les commandes utiles](#les-commandes-utiles)
  - [1. Demander au repository les dernières modifications](#1-demander-au-repository-les-derni%C3%A8res-modifications)
  - [2. Télécharger les dernières modifications](#2-t%C3%A9l%C3%A9charger-les-derni%C3%A8res-modifications)
  - [3. Les branches, d'un bel arbre](#3-les-branches-dun-bel-arbre)
  - [4. Changer de branche](#4-changer-de-branche)
  - [5. Merge](#5-merge)

## Vocabulaire de base
**Repository (repo) :** C'est la zone qui contient votre projet.</br>
**branch :** C'est une ramification d'un projet. Par défaut les projets sont sur la branche "main" dite principale. Mais quand vous devez effectuez des modifications sans toucher à la branche principale (travail en groupe ou tester un changement dont vous n'êtes pas sûr par exemple), vous pouvez créer une nouvelle branche qui vous permettra de faire une sauvegarde qui ne touche pas à votre projet principal.</br>
**merge :** C'est quand on fusionne deux version d'un projet en un seul, c'est une tâche qu'on fait souvent quand on veut passer un branche alternative sur la branche principale (main).</br>

*Pour mieux comprendre faisons un peu de jardinage*</br>
David fait pousser des pieds de tomate dans un terreau standard. Hier sur internet, il a lu qu'avec le super terreau MK2, ses tomates seraient encore plus belles et plus goûteuses. Seulement David voudrait tester ça sans brûler tous ses pieds.
Il fait donc un nouveau pot, qu'il étiquette "Test 1" pour y mettre un seul pieds de tomate avec ce nouveau terreau. Si le pied de tomate si plait et que le terreau tiens ses promesses, alors un peu plus tard, il met toutes ses tomates dans ce nouveau terreau.</br>

Il a fait donc une nouvelle "branch", qu'il a par la suite "merge".

## Les commandes à maitriser absolument
```bash
git clone
git add
git commit
git push
git status
```

### 1. Cloner un repository

On vous fourni en général un lien pour vos projet, il s'agit du lien de votre "repository". Vous pouvez le récupérer avec la commande</br>
```bash
git clone <lien> <nom>
```
Le nom est optionnel, mais vous pouvez directement en donner un pour que votre dossier soit plus agréable à regarder.</br>
exemple :</br>
```bash
git clone https://github.com/LeSpatiocorne/tuto_piscines.git bonjour
```
Cette commande clone le contenu de ce repo et appelle le dossier bonjour.</br>

### 2. ajouter du contenu
Pour ajouter du contenu à votre répository il va falloir commencer par mettre à jour les informations qu'il connait du projet.

On commence donc par ajouter les fichiers qu'il doit suivre :
```bash
git add <arguments>
```
Vous pouvez ajouter autant d'arguments que vous voulez.
Il est donc tout à fait possible d'ajouter fichier par fichier (git add ft_putstr.c ex02/) 

Mais au plus souvent vous voudrez tout ajouter d'un coup donc vous utilisez plutôt * ou .
```bash
git add .
git add *
```
**La minute culture G :** Le "." ajoute TOUS les fichiers y compris les fichiers cachés alors que "*" ajoute uniquement les fichiers normaux (donc ceux visibles par défaut).</br>

### 3. Mettre à jour l'historique
```bash
git commit -m <commentaire>
```
Le principe de commit et d'écrire l'historique de vos modification, c'est un point de repère pour la mise à jour qui vous permettra plus tard si nécessaire de retracer les changements dans leur généralité. C'est pour ça, que c'est intéressant de prendre l'habitude de donner un message court et clair de ce que vous mettez en ligne (ex: Correction dans la logique de l'ex02)</br>
Le "-m" veut dire message.

### 4. Mettre en ligne les modifications
```bash
git push
```
push veut dire "pousser", c'est le moment où vous envoyez sur le repo votre travail pour finir la sauvegarde.

### Résumer en image

Voyez toutes ces opérations comme la préparation d'un colis que vous vous envériez à vous-même.
Au moment de préparer le colis, vous faites des petites boîtes avec chaque choses pour qu'elle reste bien rangés.
Une fois que vous êtes satisfait du contenu du colis, vous l'emballez, notez les informations importantes puis l'envoyez par la poste.
C'est exactement ce que vous faites avec add - commit - push.

|add|commit|push|
|---------|---------|---------|
|remplir le colis|ajouter les infos|envoyer|

### 5. Status
```bash
git status
```
Avec git status, vous pouvez optenir l'état actuel de votre repository local, il va vous signaler les changements qui sont ajouté, ceux qui ne le sont pas, ce qui a changé.
En général quand vous avez de la couleur dans le terminal, une modification non ajouté s'affiche en rouge et une modification ajouté s'affiche en vert.
Le message est généralement construit de la façon suivante :</br>
TYPE : Nom du fichier</br></br>

ex :</br>
```ansi
\033[36;1Deleted : Ficher.c
```

## Les commandes utiles
(mise à jour en cour)
```bash
git fetch
git pull
git branch
git checkout / git switch
git merge
```
Au cour de votre aventure dans le monde merveilleux des projets de groupes, vous allez être confronté à l'expérience de ne pas toujours avoir la dernière version d'un repository sur votre ordinateur.</br>
Heureusement, git est bien fait et vous pouvez arranger ça !

### 1. Demander au repository les dernières modifications
```bash
git fetch
```
Bien que techniquement, vous pouvez vous passer de cette commande, elle reste très utile. Elle vous permet de demander ce qui a changé sur le serveur sans immédiatement tout télécharger et écraser ce qui est déjà là localement.</br>

# 2. Télécharger les dernières modifications
```bash
git pull
```
Comme le titre de cette section l'indique, pull télécharge donc la dernière version du repository sur le serveur.</br>

⚠️⚠️⚠️ Si vous avez apporté des modifications à votre repository localement alors que vous n'étiez pas sur la dernière version, git ne va pas être content du tout !</br>
Pour ne pas vous embrouyé je ne l'ai pas abordé immédiatement, mais dans la technique, git ne se contente pas de télécharger ou envoyer bêtement tout ce que vous lui donner.</br>
Il fait toujours une vérification de **différence** et ne met à jour que ce qui a changé.</br>
Si vous avez donc des modifications conflictuelles, il sera très  mécontant et vous demandera de régler le conflit avant d'aller plus loin.</br>

### 3. Les branches, d'un bel arbre

```bash
git branch <options> <args>
```
Les branches sont le top du top de l'utilisation en groupe de git !</br>
C'est votre meilleure arme contre les conflits.</br>
Vos rushs seront un cas d'usage très concret.</br>
Durant vos days et surtout pendant votre première semaine, vous vous êtes familiarisé avec les add/commit/push, mais n'avez sans doute jamais connu de conflit avec le repo distant. Ce qui est plutôt logique puisque jusqu'à present vous étiez l'unique personne à envoyer des choses dessus. Avec les projets de groupes, c'est une autre histoire. Imaginez ce qui peut se passer, si vous essayer d'écrire sur une feuille de papier à plusieur et au même endroit de la dite feuille. Ce n'est pas très chouette et d'ailleurs git sera très faché si vous essayez de faire ça.</br></br>

L'idéal est donc de faire des embranchement pour votre projet qui vont vous permettre de continuer de travailler et de sauvegarder votre travail sans vous marcher dessus.</br>
Pour créer une nouvelle branche, il n'y a pas besoin d'option vous pouvez juste lui donner un nom qui vous convient :</br>

```bash
git branch Unicorns
```
Si la branche n'existait pas après avoir utilisé cette commande, j'en ai créé une nouvelle qui s'appelle donc "Unicorns".</br>
Si c'était une erreur je peux utiliser l'option ``--delete`` pour la supprimer et si je veux consulter la liste des branches je peux utiliser l'option ``--list``
```bash
git branch --delete Unicorns
git branch --list
```

### 4. Changer de branche
Pour ça on peut utiliser deux commandes différentes, il est bon de connaître les deux car selon à quel point sera moderne votre environnement vous aurez peut-être besoin de l'une ou de l'autre.</br>
``git checkout`` et ``git switch`` ont toutes les deux pour but de changer de branche.</br>
```bash
git checkout <nom de la branche>
# OU
git switch <nom de la branche>
```
Donc si on reprends le point précédent où on avait fait une branche nommée ``Unicorns``</br>
En faisant ``git checkout Unicorns`` ou ``git switch Unicorns``, on passe sur notre branche ``Unicorns``.</br>
Une fois dessus on peut faire tout ce qu'on ferait avec la branche principale (add/commit/push/fetch/pull, etc...) et on ne touche qu'à notre branche, donc tant qu'on reste sur la bonne branche aucun risque de créer un conflit avec la principale !</br>

### 5. Merge
Enfin la dernière commande de notre petite documentation (pour l'instant ?), le merge !</br>
Elle permet de fusionner une branche avec une autre (voyez ça comme une mise en commun du travail).</br>
Pour faire ça on va passer sur la branch avec laquelle on veut merger
```bash
git checkout <branche de destination>
```
Et on merge la branche, par exemple toujours notre branche ``Unicorns``
```bash
git merge Unicorns
```
Si aucun fichier ne fait conflit, alors tout se fait automatiquement !
