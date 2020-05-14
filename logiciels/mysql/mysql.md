# mySQL

## Problèmes généraux

### Modifier le mot de passe de l'utilisateur root de mySQL

On peut toujours reconfigurer le paquet :
```shell script
# https://doc.ubuntu-fr.org/mysql
sudo dpkg-reconfigure mysql-server-5.7
```

### Créer un nouvel utilisateur super-admin

```shell script
sudo mysql
```

```mysql
# https://doc.ubuntu-fr.org/mysql
CREATE USER 'nom_utilisateur'@'localhost' IDENTIFIED WITH mysql_native_password BY 'mot_de_passe_solide';
GRANT ALL ON *.* TO 'nom_utilisateur'@'localhost';
```
