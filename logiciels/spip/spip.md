# SPIP

- [Problèmes rencontrés durant l'utilisation de SPIP](#Problèmes-rencontrés-durant-lutilisation-de-SPIP)
  * [Page blanche durant l'installation](#Page-blanche-durant-linstallation)
  * [htaccess inopérant](#htaccess-inopérant)
  * [Erreur lors d'un import de dump](#Erreur-lors-dun-import-de-dump)
  * [Mettre à jour SPIP via le spip_loader.php](#Mettre-à-jour-SPIP-via-le-spip_loader.php)
- [Astuces diverses](#astuces-diverses)


## Problèmes rencontrés durant l'utilisation de SPIP


#### Page blanche durant l'installation

Vérifiez dans les logs d'apache situés en /var/log/apache2/error.log :

```bash
cat /var/log/apache2/error.log
```

Si vous avez l'erreur suivante, c'est que php-xml-htmlsax n'est pas installée. Il s'agit habituellement d'une dépendance
de php-xml mais elle ne s'installe pas toujours en fonction du contexte. 

**_Problème :_**

```text
PHP Fatal error:  Uncaught Error: Call to undefined function xml_parser_create() in /var/www/html/nomDuSite/ecrire/xml/sax.php
```

**_Solution :_**

```bash
sudo apt-get install php-xml-htmlsax3
```

#### htaccess inopérant

**_Problème :_**

![Image d'erreur sur le .htaccess](images/spip_installation_02_erreur_htaccess.png "Erreur .htaccess")

**_Solution :_**

Renommez simplement le htaccess de l'application.

```bash
sudo mv /var/www/html/nomDuSite/htaccess.txt /var/www/html/nomDuSite/.htaccess 
```

### Erreur lors d'un import de dump

**_Problème_**

Si vous avez une erreur du type :
```text
Oups. Une erreur inattendue a empêché de soumettre le formulaire. Vous pouvez essayer à nouveau.
```

![Image d'erreur d'import du dump](images/spip_installation_04_erreur_import_dump.png "Oups. Une erreur inattendue a empêché de soumettre le formulaire. Vous pouvez essayer à nouveau.")


**_Solution_**

Il vous manque le module sqlite de PHP, (ré)installez-le :

```bash
sudo apt-get install sqlite php-sqlite3 libsqlite3-dev
```


### Mettre à jour SPIP via le spip_loader.php

**_Problème_**

Si vous avez l'erreur ___Vous n’avez pas accès à cette page.___ en appelant le fichier spip_loader.php, c'est que vous
ne vous êtes pas rajouté dans la liste des utilisateurs ayant le droit de faire cette mise à jour.

![Erreur durant la mise à jour du spip_loader.php](images/spip_installation_05_erreur_acces_spip_loader.png "Erreur accès spip_loader.php")

**_Solution_**

Allez dans l'[interface d'administration de SPIP](http://localhost/ccn/air/ecrire/?exec=auteurs) et récupérez-y votre
identifiant d'utilisateur (un nombre).

Puis vérifiez que le fichier ___spip_loader.php___ se trouve bien à la racine de votre site (aux côtés de *spip.php* et
*spip.png*). Ouvrez-le et modifiez la ligne suivante :

```php
if (!defined('_SPIP_LOADER_UPDATE_AUTEURS')) {
	define('_SPIP_LOADER_UPDATE_AUTEURS', '1:VOTRE_IDENTIFIANT_UTILISATEUR');
    // Notez la présence des deux points « : » entre les différents nombres.
}
```

La variable __SPIP_LOADER_UPDATE_AUTEURS_ contient la liste des utilisateurs ayant le droit d'appliquer la mise à jour.
Ces utilisateurs sont représentés par leurs identifiants séparés par « : »

# Astuces diverses

## Voir l'agencement des squelettes dans une page

Dans l'url de votre navigateur, ajoutez l'option :

```text
&var_mode=inclure
```

Vous aurez ainsi un affichage de page vous indiquant la provenance de chaque portion de code.

![Affichage de l'agencement des squelettes](images/spip_astuces_01_agencement_des_squelettes.png "Affichage de l'agencement des squelettes")