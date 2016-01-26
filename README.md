# Migrations

Module de gestion SQL via Doctrine Migrations.

Pré-requis : 

PHP 5.5.x | 7.x

------

Installation : 

composer require jfranclin/migrations

------

* Copier migrations-db.php.conf (ne pas supprimer) vers un nouveau fichier migrations-db.php. Configurer ce fichier avec les infos projet.
* Créer un dossier si besoin "migrations" à la racine du projet distant.
* Copier migrations.yml.conf (ne pas supprimer) vers un nouveau fichier migrations.yml. Configurer ce fichier.
* Editer le fichier migrations.yml et remplacer la dernière ligne par : migrations_directory: ../../../migrations 

Attention, le driver Pdo MySQL est requis (installer Wamp sous windows, sinon sous linux : sudo apt-get install php5-mysql).

------

Dans les VMs : 

* Dans MySQL : 

GRANT ALL PRIVILEGES ON `datbaseName`.* TO 'user'@'%' IDENTIFIED BY 'password' WITH GRANT OPTION;

FLUSH PRIVILEGES;

* Firewall :

sudo iptables -I INPUT -p tcp --dport 3306 -j ACCEPT -m comment --comment "Allow_remote"

sudo iptables-save > /etc/iptables_rules

sudo nano /etc/rc.local et ajouter avant le exit : /sbin/iptables-restore < /etc/iptables_rules


------

How To :

* Se placer dans vendor/jfranclin/migrations :

* État : php vendor/bin/migrations.php status

* Création d'une migration : php vendor/bin/migrations.php generate

* Lancer les migrations : ' php vendor/bin/migrations.php migrate 

* Annuler une migration : php vendor/bin/migrations.php migrate NUMERO_MIGRATION 

