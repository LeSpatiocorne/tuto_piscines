# L'essentiel de git

⚠️ POUR LE MOMENT CONCENTRER VOUS LES COMMANDES A MAITRISER ABSOLUMENT

## Vocabulaire de base
**Repository (repo) :** C'est la zone qui contient votre projet.</br>
**branch :** C'est une ramification d'un projet. Par défaut les projets sont sur la branche "main" dite principale. Mais quand vous devez effectuez des modifications sans toucher à la branche principale (travail en groupe ou tester un changement dont vous n'êtes pas sûr par exemple), vous pouvez créer une nouvelle branche qui vous permettra de faire une sauvegarde qui ne touche pas à votre projet principal.</br>
**merge :** C'est quand on fusionne deux version d'un projet en un seul, c'est une tâche qu'on fait souvent quand on veut passer un branche alternative sur la branche principale (main).</br>

*Pour mieux comprendre faisons un peu de jardinage*</br>
David fait pousser des pieds de tomate dans un terreau standard. Hier sur internet, il a lu qu'avec le super terreau MK2, ses tomates seraient encore plus belles et plus goûteuses. Seulement David voudrait tester ça sans brûler tous ses pieds.
Il fait donc un nouveau pot, qu'il étiquette "Test 1" pour y mettre un seul pieds de tomate avec ce nouveau terreau. Si le pied de tomate si plait et que le terreau tiens ses promesses, alors un peu plus tard, il met toutes ses tomates dans ce nouveau terreau.</br>

Il a fait donc une nouvelle "branch", qu'il a par la suite "merge".

## Comprendre le structure d'un dossier git
PART TO COMPLETE

## Les commandes à maitriser absolument
```bash
git clone
git add
git commit
git push
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
Le principe de commit et d'écrire l'historique de vos modification, c'est un point de repère pour la mise à jour qui vous permettra plus tard si nécessaire de retracer les changements dans leur généralité. C'est pour ça, que c'est intéressant de prendre l'habitude de donner un message court et clair de ce que vous mettez en ligne (ex: Correction dans la logique de l'ex02)
le "-m" veut dire message.

### 4. Mettre en ligne les modifications
```bash
git push
```
push veut dire "pousser", c'est le moment où vous envoyez sur le repo votre travail pour finir la sauvegarde.

### Résumer en image

Voyez toutes ces opérations comme la préparation d'un coli que vous vous envériez à vous-même.
Au moment de préparer le coli, vous faites des petites boîte avec chaque choses pour qu'elle reste bien rangés.
Une fois que vous êtes satisfait du contenu du coli, vous l'emballez, notez les informations importantes puis l'envoyez à la poste.
C'est exactement ce que vous faites avec add - commit - push.

|add|commit|push|
|---------|---------|---------|
|remplir le coli|ajouter les infos|envoyer|



## Les commandes utiles (mise à jour à venir)
```bash
git fetch
git pull
git branch
git merge
```