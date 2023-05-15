A faire en arrivant sur un projet symfony : 
---
Cloner le projet : 
```shell
git clone <lien_du_projet>
```
Récupérer les fichiers Composer : 
 ```shell
 composer install
 ```

* Dupliquer le fichier .env et l'appeler .env.local 
* Commenter la ligne : DATABASE_URL="postgresql://app:!ChangeMe!@127.0.0.1:5432/app?serverVersion=15&charset=utf8"
* Décommenter la ligne : #DATABASE_URL="mysql://app:!ChangeMe!@127.0.0.1:3306/app?serverVersion=10.11.2-MariaDB&charset=utf8mb4"
* Remplir cette ligne avec vos infos de DB local en suivant l'exemple : 
DATABASE_URL="mysql://your_username:your_pwd@127.0.0.1:3306/your_db?serverVersion=10.11.2-MariaDB&charset=utf8mb4"
* Vérifier que tout est bien cablé en lançant la commande : 
```sh
symfony console doctrine:database:create
```