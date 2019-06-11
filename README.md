#Cours Linux/bash


1. Histoire de linux:

#### I. Histoire de linux.

**C'est quoi Linux?** 
Linux est un système d'exploitation, au même titre que MacOS et Windows.

En 1984, Windows sort son premier OS: MS-DOS. À ce moment , un autre OS existe, c'est UNIX (depuis 1969) Mais il est beaucoup plus compliqué à utiliser, et donc réserver au pro.

Là même année(1984), Richard Stallman, chercheur ou MIT voulais crée son propre système d'explotation, fonctionant comme Unix. Sa volonté venais du fait que le système Unix devenais de plus en plus chère. Richard Stallman devint le fer de lance du libre et fonda le projet GNU.
Pour Richard Stallman le progrès passe par la **coopération** et pour cela tout le monde dois avoirs accès au code souce de chaque programme. Avoir la liberté de le modifier pour l'amélioré et de pouvoir ensuite redistribuer ce programme à la communauté.
Il commenca donc à développer des **versions libre des programmes Unix**.

**En 1991 Linus Torvalds**, étudiant finlandais, entreprend de crée son propre sytème d'exploitation. Ce système s'appelle Linux, la contraction de Linus et Unix.
En fait Linus lui c'est lancé dans la création du coeur de linux. Et les programmes libre du projet GNU ont complèté ce coeur pour arriver au résultat **GNU/linux**.

En vérité nous devrions toujours parler de GNU/Linux, car c'est cette assosiaction qui donne ce que nous appelons Linux.

Aujourd'hui, il y as un certain nombre de distribution de linux:
[Lien wiki liste distribution Linux](https://fr.wikipedia.org/wiki/Liste_des_distributions_Linux).
À savoir: Toute les disto. partage le même coeur, change l'instalation, les programme pré-installé et le manager de programme.
Les deux famille principale sont RedHat (serveurs) et Debian (Ex: Ubuntu).

Voici un lien sur les "part de marché" de Linux. (difficile de mesurer les part de marché de quelque chose de gratuit):
[Part de marché Linux](https://fr.wikipedia.org/wiki/Linux#Parts_de_march%C3%A9).

#### II. Le système de fichier de Linux.

Sous Unix, le système de fichier est d'une conception assez différente que celle de Windows. Sous Unix tout est considéré comme un fichier, même un lecteur CD ou une clé USB. Comme tout est un fichier il est possible d'avoir des fichiers sans extension. Les disques (comme le `C:` le `D:`,le ` E: `etc..)sont juste des fichier spéciales qui sont monté sur le système de fichier.

Donc il n'y as pas de `C:`, sur Linux tout commence à la racine notée `/`.
Il y as ensuite un certain nombres de dossier, voici ceux qui nous intéresse: 

Répertoire | Rôle remplis
-|-
`home/`| Contient les répertoires personnels des utilisateurs.
`var/`| Contient les données variables (logs par exemple).
`bin/`| Contient les programmes commun a tout les utilisateurs.
`usr/`| Contient les programmes des utilisateurs.
`etc/`| Contient les fichiers de configuration.
`opt/` | Contient les _add-ons_ des programmes.
`lib/` | Contient toutes les librairies des programmes.



#### III. La console.

** La console linux (le Terminal)**
![Une console vide](/home/kuk666/programation/linux/img/console-vide.png  "Le Terminal")

La console un le moyen de contrôler un ordinateur. Une interface graphique est un autre moyen, mais même si il est plus intutif, il est aussi plus limité car certaine action de sont pas possible (ex. l'utilisation de `npm`, de `git` ou tout autre programme s'utilisant avec une CLI _"Command Line Interface"_).

L'utilisation est simple, l'invite de commande attend la commande entrée par l'utilisateur.
On peut décomposer l'invite de commande de cette façon:

Login/Pseudo | Chez | nom de l'ordinateur | séparateur | dossier actuel | niveau d'autorisation
-|-|-|-|-|-
kuk666 | @ | kuk666 | : | ~ | $ 

À chaque fois que je commence un morceau de code j'utilise `$` pour indiquer la fin de mon invite de commande. Cela donne ` $ commande `

![console sorties](/home/kuk666/programation/linux/img/console_sorties.gif  "console sorties")

Une fois la commande executé, la console retourne soit une erreur (ici la comande `$ tre`n'existe pas), soit le resultat de la commande (ici `$ ls`retour la liste des fichiers du repertoire courant).

Ces deux sortie s'affiche par défaut dans la console, mais nous verront plus loin qu'il est possible de très facilement changer cela.

#### IV. Les commandes.

Les commandes peuvent être considéré comme des fonctions.  Elles peuvent être appelé avec ou sans paramètre. 

![ls avec et sans paramètre](/home/kuk666/programation/linux/img/ls.gif  "ls avec et sans paramètre")

On voit ici que la commande `ls` (`ls` pour _list_) utilisée seule liste le contenu du dossier courant. On peut aussi lui donner en paramètre le chemin du dossier à lister. Enfin on peut donner des **options** à la commande (Les options commence toujours par `-` ou par `--`). 

**Les options :**

Les options sont _soit_ une option courtes, qui s'écrit avec un seul tiret `-` (par exemple `-a`, `-v`, `-l`etc.), _soit_ une option longue qui s'écrit avec deux tiret `--`(par exemple `--version`).
Les options courtes peuvent être combiné ensemble (par exemple `-la` est la combinaison de `-a` et `-l`).

**Liste des commandes de base :**

Commande | Nom | Description 
-|-|-
`$ ls`| _list_ | Renvoi la liste du contenu du dossier courrant.
`$ cd chemin/dossier1/` | _change directory_ | Va au dossier `chemin/dossier1/`.
`$ mkdir nomDossier/` | _make directory_ | Crée le dossier `nomDossier/` dans le répertoire courant.
`$ rm fichier` | _remove_ | Supprime `fichier`. Si la cible est une dossier il faut rajouter l'option `-r`.
`$ touch nomFichier` | _touche_ | Touche un fichier pour simulé une ouverture. Si le fichier n'existe pas, il est crée.
`$ mv Source Destination` | _move_ | Déplace le fichier soure à la déstination, si le fichier déstination porte un autre nom, le nom du fichier sera modifier.
`$ cp Source Destination` | _copy_ | Copie le fichier source à la déstination. (option `-R` pour copier un répertoire).
`$ pwd` | _print working directory_ | Affiche le chemin du répertoire courant.
`$ ln ` | _link_ | Permet de crée des liens physique ou symbolique.

Un certain nombre ont de nombreuses et utiles options, voici les plus importante:

**Pour `ls`:**

Option | Description
-|-
`-a` | --all liste tout les fichiers, même caché.
`-l` | affiche une liste détaillé.
`-h` | taille en ko,go etc.. (Human readable).
`-t` | trier par date de dernière modification.

Et 60 autres options. Par la suite nous verrons comment voit le manuel des commandes.

**Pour `rm` :**

Option | Description
-|-
`-i` | Demander confirmation.
`-f` | Forcer la suppression.
`-v` |_--verbose_ Affiche les actions exécuter par la commande.
`-r`| _--rescursive_ supprime le dossier et son contenu

Linux protège les données et bloque l'accès aux donnée sensible, mais comme toujours sur linux il suffit de passer en super-utilisateur (root)

#### Exemple : 

**`$ cd` :**

![exemple utilisation cd](/home/kuk666/programation/linux/img/cd.gif  "exemple utilisation cd")

**`$ ls` :**

![ls -l -a](/home/kuk666/programation/linux/img/ls2.gif  "ls -l -a")

**`$ mv` :**

![mv commande](/home/kuk666/programation/linux/img/mv.gif  "mv commande")

le fonctionnement sera similaire avec `cp`.


Pour finir ses quelque exemples, voici comment utiliser le Joker `*`:

![joker](/home/kuk666/programation/linux/img/utilisation_joker.gif  "joker")
**Liste des commandes d'affichage :**

Commande | Description 
-|-
`$ cat` | Concatène le(s) fichiers et les affiches d'un coup.
`$ less` | Affiche page par page. Voici quelques raccourci : `q` quitte la lecture, `Espace` affiche la page suivante, `/` permet de faire une recherche (tapé `n` pour navigué au résultat suivant).
`$ head` | affiche le début du fichier (l'option `-n` permet de choisir le nb de lignes à afficher).
`$ tail` | affiche la fin du fichier (l'option `-n` fonctionne pareil, il s'ajoute `-f` pour _follow_ qui permet de suivre le fichier). Faire Ctrl-c pour arrêter la commande.

#### RTFM Lire le manuel :

Ils y as beaucoup, beaucoup de commande. Sur Ubuntu il y as plus de 2000 commandes insallées de base, et il y en as beaucoup plus, et il est facile d'en crée d'autre.
Il n'est donc pas possible de les connaitres toute et encore plus illusoire de connaitre toute les options de chacune de ses commandes. Il est donc indispensable de savoir lire documentation de bash. 

Si vous poser la question _"comment afficher un fichier avec `less`?"_ sur un forum, on vous dira surment: **RTFM**. Autrement dit **Read The Fucking Manual**. Autrement dit, lit le manuel avant de posé ta question!!!

Comment faire pour lire la doc d'une commande? Rien de plus simple, il suffit de précéder la commande de la commande `man`. Cela donne quelque chose de cette forme: `$ man ls`.

Et voici le résultat:
![man ls](/home/kuk666/programation/linux/img/man_ls.gif  "man ls")

La ligne qui nous interesse ici est le **SYNOPSIS**. il peut être très simple, comme celui de la commande `ls`:

![man ls](/home/kuk666/programation/linux/img/Syn_ls.png  "man ls")

Ou très complexe comme le `man` de la commande `apt`:

![man apt](/home/kuk666/programation/linux/img/man_apt.png  "man apt")

Regardons ca d'un peu plus près, avec le synopsis de la commande `ls`.

**`ls`** `[OPTION]...` `[FILE]...`

1.**`ls`** : Le nom de la commande. Le mot est en **gras** ce qui veut dire qu'il doit être écrit exactement comme indiqué.

2.__`[OPTION]...`__ : Là il y as plusieurs choses. Les crochets `[]` qui signifie _facultatif_, ce qui veut dire que l'on _peut_ ne pas renseigner d'option. 
Le soulignage (si si il est sur la capture d'écran.) nous informe que le mot OPTION est as remplacer. Donc il faudra par exemple écrire `-a` à la place de `OPTION`. 
Enfin les **`...`** indique que le paramètre qui précède peut être répété **autant** de fois que vous voulez.

3.__`[FILE]...`__ : même chose que pour option sauf que ctete fois c'est le chemin d'un fichier qui est attendu plutôt qu'une option.

En francais, **`ls`** `[OPTION]...` `[FILE]...`, signifie _Taper la commande `ls` suivi d'un nombre d'option voulu, puis des chemins voulu.


Dans le deuxième exemple on peut voir aussi le pipe `|` qui dans le man représente le **OU Exclusif** logique. Par exemple `{-v | --version}`, je dois soit utiliser `-v`, soit utiliser `--version`, mais pas les deux en même temps.

Syntaxe | Signification
- | -
**`gras`** | Écrire le mot tel quel.
`mot souligné` | Dois être remplacer par la valeur qui convient.
`[]` | Ce qui est entre crochet est facultatif.
a`| `b | OU EXCLUSIF, ici c'est soit a, soit b.
x`...` | Indique que x peut être répéter autant de fois que vous voulez.

#### Les droits:

Linux est un système multi-utilisateurs, ce qui veut dire que plusieurs personne peuvent travailler simultanément sur le même système. 

Pour la stabilité d'une telle organisation il est obligatoire d'avoir des droits bien définit pour chaque utilisateur. De base sur un système Unix il y as 2 utilisateur. Vous (moi c'est `kuk666`)  et le Super-Utilisateur (`root`). On peut ensuite ajouter autant d'utilisateur que l'on veut, et les rassembler en groupe.
Sous Unix chaque fichier possède un propriétaire. Il y as trois droits possible sur un fichier, le droit de lecture (`r`), d'écriture (`w`) et d'execution (`x`). 
Pour chaque fichier est définit les droits son propriétaire, les droits du groupe et les droits des autres utilisateurs.

Pour connaitre les droits et l'appartenance d'un fichier il existe un commande... `ls`! Plus précisément `ls -l`. Par exemple:

![droits](/home/kuk666/programation/linux/img/ls_droits.png  "droits")

Les quatres premières colone en partant de gauche sont les droits. la forme est toujours la même. Soit il y a un tiret `-`, soit un caractère.
La première colonne donne une infomation sur le type. Soit c'est un dossier `d`, soit c'est un lien `l`. Le tiret `-` signifie que c'est _juste_ un fichier.

Ensuite chaque colonne donnes les trois droits de l'utilisateur (colonne 2), du groupe, et du reste du monde (4ème colonne)

colonne 1 | colonne 2 | colonne 3 | colonne 4
- | - | - | -
`d` | `rwx` | `rwx` | `rwx`
Type | Utilisateur | Groupe | Autres

Soit le droit est activé, et dans ce cas c'est le caractère du droit en question, sinon si c'est un tiret, le droit n'existe pas. On parle ici d'un triplet de droits.

Ensuite sur les colonnes 5 et 6 on trouve respectivement le propriètaire du fichier, puis le groupe propriétaire.

Analysons le fichier 1, nous avons:

1 | 2 | 3 | 4 | 5 | 6
-|-|-|-|-|-
`-`| `rwx` | `rwx` | `---` | `root` | `root`
tiret donc c'est un fichier | tout les droit sont activé pour le proprietaire | tout les droits sont activé pour le groupe | aucun droit pour les _autres_ | Le propriétaire est `root` | le groupe propriétaire et `root`

On voit que `dossier1` à un droit d'execution pour tout le monde. En fait pour linux un dossier est un fichier particulier. Et pour pouvoir ouvrir un dossier et naviguer dans ses sous-dossiers il faut pouvoir executer ce _fichier_.

**Changer les droits d'un fichier ?**

Le seul qui peut modifier les droits est `root`! Pour pouvoir executer une commande en root il faut précèder la commande de la commande `sudo`. (`sudo` veut dire **S**ubtitute **U**ser **DO** _"faire en se substituant à l'utilisateur"_). On vous demandera de taper votre mot de passe pour valider l'execution de la commande. (pas de panique si vous ne voyer pas d'étoile quand vous taper votre mot de passe, linux _cache_ le nombre de caractère que vous tapé).

**Attention :** En tant que super utilisateur vous avez **TOUS** les droits. Vous devez donc être sur de ce que vous faite à ce moment là car personne ne pourras vous empêcher de faire des grosse bêtise !!!

_Exemple:_

![sudo](/home/kuk666/programation/linux/img/sudo.gif  "sudo")

Pour modifier les droits d'un fichier il faut utiliser la commande **`chmod`**, soit de manière absolu, soit de manière relative.

**Chmod absolu :**

On peut attribuer des droit avec des chiffres, chaque droit correspond à chiffre, et pour savoir quels droits on attribut à un triplet, on fait une addition.

Correspondance droit/chiffre:

Droit | Chiffre
-|-
`r` | 4
`w` | 2
`x` | 1

Total des droits:

Droits | Chiffre | Calcul
-| - |-
`---` | 0 | 0 + 0 + 0
`r--` | 4 | 4 + 0 + 0
`-w-` | 2 | 0 + 2 + 0
`--x` | 1 | 0 + 0 + 1
`rw-` | 6 | 4 + 2 + 0
`-wx` | 3 | 0 + 2 + 1
`r-x` | 5 | 4 + 0 + 1
`rwx` | 7 | 4 + 2 + 1

Cela peut parraitre un peu complexe au premier abord, mais dès que l'on as un peut l'habitude c'est très rapide car il suffit de faire `$ sudo chmod 700 fichier1` pour donner tout les droits au propriétaire de `fichier1`, mais aucun droit au groupe et aux autres utilisateurs.

** Chmod relatif :**

Un autre moyen de modifier des droits est d'utiliser des lettres.

Lettre ou opérateur | signification
-|-
`u` | user (le propriétaire)
`g` | group (groupe)
`o` | other (tout les autres)
`+` | ajouter un droit
`-` | supprimer le droit
`=` | affecter le(s) droit(s)

On peut facilement changer des droits de cette façon. `chmod g+w fichier1` donne le droit d'écriture au groupe. `chmod u+rx fichier1` donne les droits de lecture et d'execution au propriétaire.`chmod u=rwx, g=r, o=- fichier1 ` donne tout les droits aux propriétaire, le droit de lecture au groupe et rien aux autres.

Pour finir si l'on veut changer les droits d'un dossier et que cela soit répercuté sur chacun des fichiers et sous dossiers contenu, il faut utiliser l'option `-R` (**R**ecursive)!

#### Installer des programmes :

Installer un programme sur linux est vraiment simple. La plus part des programmes linux son rasemblé sur des seveurs que l'on appelle dépôts. Ils partage tous le même contenu. Le serveur par défaut est le plus proche géographiquement.

En fait sous linux un programme peut rarement fonctionner seul, il as besoin de bibliothèque. Heureuseument le système de paquets Débian est intelligent, il ira checher seul toute les dépendance manquante. Ce qui n'est pas le cas sur toute les distro.

Comment instaler un programme sur linux? Avec la commande `apt`. Comme vu dans l'exemple plus haut, le synopsis de la commande `apt` est asser complexe, la commande permet beaucoup de chose. Mais voici les deux formes les plus utile:

* `apt-cache search votrerecherche` permet d'effectuer une recherche dans le dépot. Le retour de la commande est la liste de tout les programme qui contenait le mot clé `votrerecherche`.
* `apt-get install paquet` permet d'installer le paquet.

**exemple :**

![apt-get](/home/kuk666/programation/linux/img/install-Breakout.gif  "apt-get")

Dans cet exemple je commence par chercher un jeu de casse brique (breakout). ensuite j'installe le paquet `lbreakout2`. Cela me demande mon mot de passe car pour installer un programme je dois être en Root (Super Utilisateur). 
On me donne des information sur le contenut du paquet et les dépendances dont il as besoin pour fonctionner, et On nous demande si nous voulons continuer. 

Si on répond oui, la magie d'`apt-get` opère: Le programme va aller télécharger toutseul le paquet sur le dépot ainsi que toute les dépendances dont il a besoin et que nous n'avons pas. Puis il _dépaquète_ les fichiers qui était à l'intérieur du paquet, les installes et effectue les paramétrage tout seul.

Enfin voici une dernière commande, pour désinstaller un paquet: `apt-get autoremove paquet`. Notez ici `autoremove` permet aussi de désintaller les librairies inutile.

#### Rechercher des fichiers :

Pour rechercher des fichier il y as deux commandes, `locate` et `find`. La première est très simple et la deuxième peut devenir très (très très très) complexe.

**`locate` :**

Linux contient une base de donnée qui est un index de tout les fichier du disque dur. La base de donnée ce met à jour 1 fois par jours. 
`locate` permet de chercher dans cette base de donnée, et permet de retrouver un fichier **très rapidement**. Son inconvéniant est que si le fichier viens juste d'être crée, il n'apparaitra pas dans le recherche car il n'est pas encore inscrit dans la base de donnée. On peut forcer la mise à jour de la BDD grace à la commande `sudo updatedb`, mais cette dernière prend un certain temps, donc autant utiliser directement `find`. 

**`find` :**

`find` elle ne fait pas un recherche dans la base de donnée, mais parcours le systeme de fichier depuis l'endroit spécifier, ce qui peut être long. (Si vous avez 500Go et que vous lancez une rechreche à la racine `\`, vous pouvez aller boire un café tranquille !!).

Le fonctionnement de `find` est le suivant:
**`find`** _`Où`_ _`Quoi`_ _`Que faire avec`_

Seul le _`Quoi`_ est obligatoire. Si le _`Où`_ n'est pas spécifier, `find` se lance dans le fichier courant, et si _`Que faire avec`_ n'est pas spécifier non plus, la commande ce contente d'afficher le résultat de la recherche dans la sortie standard (la console).

Développons maintenant chacun de ses trois paramètres.

**Où :**

C'est sans aucun doute le plus simple à utiliser, puisqu'il suffit d'indiquer le nom du repertoire dans lequel va s'effectuer la recherche. Gardez tout de même à l'esprit que plus la commande va avoir de chemins à parcourir plus elle sera longue à s'éxécuté.

**Quoi :**

Là on as envie de dire que c'est simple et qu'il suffit de mettre le nom du fichier que l'on cherche, mais ca serait passer à côté d'une grande partie de la puissance de `find`.

En fait on peut chercher un fichier par d'autre moyen que son nom. Voici une partie des possibilité du `Quoi`:

Test | Signification
-|-
`-name` _`motif`_ | Rechercher les fichier qui corespondent exactement au motif fourni. Attention,  pensez à entourer le motif du joker (_`*motif*`_) si vous voulez inclure les résutat qui ne sont pas exactement _`motif`_.
`-size` _`n`_`[cwbkMG]` | rechercher par taille de fichier. _`n`_ est a remplacer par un nombre. Il est préfixer de `+` ou `-`et suffixer d'une des lettres entre crochet (M = Mo, G = Go). 
`-atime` _`n`_ | dernier accès au fichier il y a _`n`_*24 heures.
`-perm` _`mode`_ | Fichier dont les autorisations d'accès sont fixées exactement au mode indiqué (en notation symbolique ou octale). 
`-user` _`utilisateur`_ | fichier appartenant à l'_`utilisateur`_ indiqué.

C'est une liste non-exaustive, pour connaitre toute les posibilité pour le `Quoi` lisez le man. Ce ne sont pas des options exclusive, ce qui veut dire que vous pouvez combiner ses test ensemble. Par exemple si je cherche un fichier `.jpg` auquel je suis sur d'avoir eu accès il y as 3 jours, et je sais qu'il fait moins de 2Mo et qu'il m'appartient. Cela donne: `$ find ~ -name "*.jpg" -size -2M -atime 3 -user moi`

**Que faire avec :**

Allez, ca c'était la partie facile de la commande `find`, maintenant voici ce qui fait que la commande `find` est si puissante.

Que faire avec? Nous avons dit plus haut que par défault, la commande `find` affiche le résultat dans la console. En fait, `find` est executer avec l'option `-print`. 

Il y as plusieurs option qui permette de formater la sortie, et de l'envoyer dans un fichier plutôt que la console. Il faut absolument connaitre `printf`_`format`_ qui permet de choisir de manière très précise qu'elle information du fichier afficher (parmis les méta-donnée) et permet aussi d'ajouter du texte personaliser.

Au delà des notion de format, l'option qui fait toute la puissance de find est `-exec`_`commande`_. Cela permet d'utiliser une commande  pour chacun des résultats! et vous pouvez executer presque toute les commandes. La syntaxe est composé de quatre élements:

Élement | signification
-|-
`-exec` | executer
`commande`| la commande que l'on veut executer
`{}`| Les accolades prendrons pour valeur chacun des résultats que `find` va trouver.
`\;`| Est pour indiquer que l'on est arriver à la fin de la commande

Comment faire si je veux copier toute les images .jpg de mon disque dur dans un autre dossier ?
**exemple :**

![find -exec](/home/kuk666/programation/linux/img/findExec.gif  "find -exec") 

Ici j'ai volontairement brider la commande avec l'option `-maxdetph 1` pour que find ne descende pas plus en profondeur dans l'arborescence que 1 étage soit le dossier courant, ceci pour ne pas faire un gif ou rien ne se passe, le temps que la commande s'execute.

#### Les flux de donnée :

Nous avons vu plusieurs fois la notion de sortie standard, mais aussi la sortie d'erreur. Ici nous allons voir comment maitriser les flux de donnée. 

Prenons pour exemple la commande `ls`. Nous nous rappelons qu'elle sert a lister les fichier contenu dans le dossier donner en argument. Si aucun dossier n'est précisé, c'est par defaut le répertoire courant qui sera listé. 

Nous avons deux possibilités, soit le chemin du dossier est valide et `ls` nous affiche la sortie standard (le résultat). Dans le cas où le dossier n'est pas valide, il y as une deuxième sortie possible, la sortie d'erreur.

Nous avons donc, pour chaque commande **deux** sortie possible et **distincte :** La sortie standard et la sortie d'erreur: par défaut ces deux sortie s'affiche dans la console, c'est pour cette raison que nous ne faisons pas forcement attention à cette distinction, mais cela sera utile pour la suite.

Si c'est un comportement par défaut cela veut dire que l'on peut faire autrement!

**Rediriger le résultat dans un fichier :**

Imaginons que nous souhaitions conserver la liste de tout les film qui sont dans notre dossier Vidéo, pour par exemple la partager. Comment feriez vous en graphique???
En console en tout la c'est très simple il suffit d'ajouter en fin de commande le chevron fermant `>` suivi du nom du fichier dans lequel ecrire la sortie standard. Si le fichier n'existe pas, il est crée. 

Cela donnerais quelque chose comme ca: 
`$ ls /home/kuk666/Video/ > sortie.txt`

Attention, le "problème" du chevron simple c'est que si le fichier cible existe déjà, il est écraser. Pour simplement ajouter du contenu à celui déjà existant, il nous faudra utiliser les double chevron fermant `>>`.

Petite présision ici, nous parlons bien de redirigé la sortie standard de la commande. Avec cette manière de faire, les erreur s'afficherons quand même dans la console.

**Le trou noir de Linux**

Vous pourriez avoir envi de ne voir la sortie standard ni dans un fichier ni dans la console. Dans ce cas vous pouvez la rediriger dans le trou noir de linux, le repertoire `/dev/null`. Pourquoi le trou noir? Tout simplement que tout ce qui entre dans ce répertoire disparait irrémédiablement... 
