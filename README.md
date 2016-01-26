# migrations

Module de gestion SQL via Doctrine Migrations.

Installation : 

Copier migrations-db.php.old (ne pas supprimer) vers un nouveau fichier migrations-db.php. Configurer ce fichier.

------

How To :

État : php vendor/bin/migrations.php status
------
Création d'une migration : php vendor/bin/migrations.php generate
------
Lancer les migrations : ' php vendor/bin/migrations.php migrate 
------
Annuler une migration : php vendor/bin/migrations.php migrate NUMERO_MIGRATION 
------
