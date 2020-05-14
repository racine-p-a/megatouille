# Ubuntu

## Étapes post-installation Ubuntu 20.04

```shell script
sudo apt update
sudo apt upgrade
sudo apt install git yakuake filezilla
sudo apt install apache2 mysql-server php phpmyadmin postgresql php-pgsql sqlite3
```

### Configurer mySQL

#### Créer un nouvel utilisateur avec droits admin

```shell script
sudo mysql
```

```mysql
# https://doc.ubuntu-fr.org/mysql
CREATE USER 'nom_utilisateur'@'localhost' IDENTIFIED WITH mysql_native_password BY 'mot_de_passe_solide';
GRANT ALL ON *.* TO 'nom_utilisateur'@'localhost';
```

### Configurer postgreSQL

Pour se [créer un utilisateur avec les droits sur une base](../../logiciels/postgresql/postgresql.md#crer-un-nouvel-utilisateur-super-admin).

### Importer FileZilla

### Configuration générale

Remplacer le lanceur d'applications par un menu d'applications.

Raccourcis barre de lacement :
- Konsole
- Firefox
- Ktorrent
- FileZilla

### Configurer Yakuake

- hauteur : 30%
- largeur : 90%
- thême : Breeze Perfect Dark



### Installer d'autres logiciels

Installer les logiciels suivants :
- [PhpStorm](https://www.jetbrains.com/phpstorm/)

Options à modifier :

- modifier le clavier : French (alt. Latin-9 only)


## Connaître sa version d'Ubuntu

En ligne de commande, il suffit de :

```bash
lsb_release -a
```

Ce qui nous donnera :

![Connaître sa version d'Ubuntu](images/ubuntu_release_name.png "Connaître sa version d'Ubuntu")