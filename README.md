UE L222 - CIEL 2
==================================

## Environnements ##

Vous avez trois possibilités pour installer ce projet : 
  * l'installer au sein de votre environnement "*hosting*" mis à disposition par l'Université
  * utiliser Docker sur votre propre ordinateur par l'intermédiaire de [Docker Desktop](https://docs.docker.com/docker-for-windows/install/)
  * ou utiliser l'outil Symfony CLI : **cette méthode est recommandée**

Si vous utilisez le logiciel [Docker Desktop](https://docs.docker.com/docker-for-windows/install/), vous pouvez utiliser l'image Docker "[bspcvtic/cvtic-lamp](https://hub.docker.com/r/bspcvtic/cvtic-lamp)". Les modalités d'installations sont les mêmes que celles présentées pendant cette UE. 

**Nous vous recommandons néanmoins l'usage de [Symfony CLI](https://symfony.com/download#step-1-install-symfony-cli)**. Si ce logiciel n'est pas installé sur votre ordinateur, la procédure a suivre est précisée sur le site de l'éditeur : [https://symfony.com/download#step-1-install-symfony-cli](https://symfony.com/download#step-1-install-symfony-cli). Le logiciel PHP doit également être installé sur votre ordinateur.

**La configuration logicielle de ce projet est sensiblement la même que celle utilisée pour les mini-projets des semaines 3 et 4. A noter que le système de stockage des données utilisé est SQLite3**

## Lancement du projet ##

Après avoir récupéré les sources du projet, procédez à son installation, selon l'environnement que vous aurez retenu. Dans tous les cas, il vous faudra utiliser le logiciel **[Composer](https://getcomposer.org/download/)** pour télécharger les dépendances, par l'intermédiaire de la commande `composer install`, à executer à la racine du projet.

N'oubliez pas d'initialiser la base de données et son contenu. Pour ce faire, executer les commandes suivantes : 
  * `php bin/console make:migration` : prépare la migration des données
  * `php bin/console doctrine:migrations:migrate` : rend effectifs les modifications en base de données
  * `php bin/console doctrine:fixtures:load` : injecte les *"fixtures"*, c'est à dire les données par défaut, en base de données

**Si vous avez choisi l'installation de Symfony avec Symfony CLI :**
  * ouvrez un invité de commande, un Power Shell ou un terminal (selon votre système d'exploitation) à la racine de votre projet
  * executer la commande `symfony serve` afin de lancer le serveur

Puis enfin, accédez au projet Symfony par l'intermédiaire de votre navigateur, en saisissant l'URL 
  * par exemple [http://localhost:1234](http://localhost:1234) : si vous avez choisi d'utiliser **Docker Desktop** avec une redirection vers le port 1234
  * si vous avez choisi **Symfony CLI**, l'**URL a saisir est retournée lors de la commande** `symfony serve` sur le principe (par exemple : http://127.0.0.1:8000)


## Présentation du projet ##

Le projet proposé pose les bases d'une gestion de menu. Ce projet simpliste gère des **plats** et des **catégories de plat**

Pour chaque plat, une gestion [CRUD](https://fr.wikipedia.org/wiki/CRUD) est déjà implémentée, avec des interfaces déjà mise en place : listing / édition / ajout / suppression de données. Il en est de même pour les catégories de plat.

Les **`Plats`** sont définis par les caractéristiques suivantes :
  * `id` : identifiant unique du plat
  * `titre` : titre du plat
  * `category` : catégorie du plat -> liaison avec les données **`Category`**
  * `description` : contenu du plat

Les **`Category`** seront définies par les caractéristiques suivantes : 
  * `id` : identifiant unique de la catégorie
  * `name` : nom de la catégorie


## Consignes de réalisation ##

En vous basant sur le code proposé, vous proposerez l'**enrichissement d'interface** de l'outil. 
Il vous faudra donc : 
  * ajouter Bootstrap au projet, de la manière la plus adaptée
  * personnaliser en CSS et en Javascript ***(au choix)*** la totalité des pages du site internet
  * gérer aux mieux vos *assets* (fichiers CSS, JS, images, ....)
  * ajouter un champ `description` aux catégories et intégrer sa gestion et son affichage aux différentes pages du projet
  * déposer votre production sur un espace Git suivant les consignes précisées dans le sujet du CIEL (format PDF)


## Rappels d'URL du projet ##

  * Page d'accueil : redirection vers http://VOTREURL/plat
  * Page de listing des plats http://VOTREURL/plat
  * Page de détails d'un plat dont l'identifiant unique est **1** : http://VOTREURL/plat/1/
  * Page d'édition d'un plat dont l'identifiant unique est **1** : http://VOTREURL/plat/1/edit/
  * Page d'ajout d'un plat : http://VOTREURL/plat/new/
  * Page de listing des catégories : http://VOTREURL/category
  * Page de détails d'une catégorie dont l'identifiant unique est **1** : http://VOTREURL/category/1/
  * Page d'édition d'une catégorie dont l'identifiant unique est **1** : http://VOTREURL/category/1/edit/
  * Page d'ajout d'une categorie : http://VOTREURL/category/new/

