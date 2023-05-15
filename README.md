A faire en arrivant sur un projet symfony : 
---
* Installer composer : 
Tout d'abord ouvre un terminal et rends toi dans le dossier de ton projet.
    - Exécute les commandes suivantes (une par une) afin de télécharger composer dans le dossier de ton projet :
    ```shell
    php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
    php composer-setup.php --filename=composer
    php -r "unlink('composer-setup.php');"
    ```
    - Puis installer le fichier que je vais vous envoyer.
    - Vérifier que composer est bien installé :
    ```shell
    composer --version
    ```
    - Pour être sûr d'avoir Composer à jour : 
    ```shell
    composer self-update
    ```

* Cloner le projet : 
```shell
git clone <lien_du_projet>
```
* Récupérer les fichiers Composer : 
 ```shell
 composer install
 ```

* Dupliquer le fichier .env et l'appeler .env.local 
* Commenter la ligne : DATABASE_URL="postgresql://app:!ChangeMe!@127.0.0.1:5432/app?serverVersion=15&charset=utf8"
* Décommenter la ligne : #DATABASE_URL="mysql://app:!ChangeMe!@127.0.0.1:3306/app?serverVersion=8.0.32&charset=utf8mb4"
* Remplir cette ligne avec vos infos de DB local en suivant l'exemple : 
DATABASE_URL="mysql://your_username:your_pwd@127.0.0.1:3306/your_db?serverVersion=10.11.2-MariaDB&charset=utf8mb4"
* Vérifier que tout est bien cablé en lançant la commande : 
```shell
symfony console doctrine:database:create
```
* Installation du module Webpack encore: 
```shell
composer require symfony/webpack-encore-bundle
```
* Installation NVM, Node, NPM et Yarn : 

1. NVM (Node Version Manager)
À la page https://github.com/coreybutler/nvm-windows/releases, tu trouveras l'accès pour télécharger la dernière version de l'installeur nvm-setup.zip.
Télécharge et décompresse le fichier zip et lance le programme nvm-setup.exe qui va s'occuper d'installer nvm.

2. Installation de Node et NPM
Comme tu l'as vu en début de cette quête, il est fortement recommandé d'utiliser la version Active LTS de Node. Vérifie quelle est la version actuellement en cours à la page https://nodejs.org/en/about/releases/ puis, dans un PowerShell (avec accès admin - touches [Windows + X]), sers-toi de nvm pour l'installer avec la commande nvm install <version> en remplaçant <version> par le bon numéro.

Exemple pour la version 18 : nvm install 18

À la fin de l'installation, tu es invité à saisir la commande nvm use <version_installée> (exemple : nvm use 18.12.1) pour l'activer.
Tu peux vérifier que tu as bien Node et NPM avec node -v et npm -v.

3. Installation de Yarn
Dernière étape, installe Yarn avec NPM.
La commande à exécuter avec npm est disponible sur la documentation https://classic.yarnpkg.com/en/docs/install/. Tu dois y trouver quelque chose comme ceci
sh npm install --global yarn

Vérifie avec yarn -v.

Note
Essaie d'accéder à Yarn avec Gitbash (que tu utilises régulièrement maintenant). Si aux retours des commandes node -v, npm -v ou yarn -v tu obtiens command not found, c'est qu'il te faut ajouter le chemin vers le répertoire /nodejs à tes variables d'environnement. Ajoute à la variable PATH l'entrée C:\Program Files\nodejs et cela devrait suffire. Il se peut cependant que tu aies à adapter le chemin en fonction de la configuration de ta machine.

Et voilà ! 🎉

Voici un petit tuto récapitulatif pour NVM, Node et NPM si tu as rencontré des problèmes à l'installation https://docs.microsoft.com/fr-fr/windows/dev-environment/javascript/nodejs-on-windows.

* Installation des dépendances du projet: 
```shell
yarn install
```
* Installation sass-loader pour compiler du SCSS
    Decommenter l'option .enableSassLoader() dans le fichier webpack.config.js puis :
```shell
yarn add sass-loader@latest sass --dev
```

Commandes utiles 
---
* Créer un formulaire : 

```shell
php bin/console make:form
```
Il te demande :

Le nom de la classe de formulaire que tu veux (CategoryType) et si tu oublies le Type final il le rajoute pour toi

Le nom de la classe de données associée (Category)

