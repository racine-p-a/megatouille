# postgreSQL

## Problèmes généraux

### Créer un nouvel utilisateur super-admin avec sa table correspondante

```shell script
#Identifiez-vous en tant que postgres :
sudo -i -u postgres
# Lancez postgres
psql
```

```postgresql
-- voir source  : https://doc.ubuntu-fr.org/postgresql

-- Créez votre utilisateur :
CREATE USER nouvel_utilisateur;
-- Donnez-lui des droits de création de base :
ALTER ROLE nouvel_utilisateur WITH CREATEDB;
-- Créez la table et assignez-en la propriété à votre utilisateur :
CREATE DATABASE nouvelle_base OWNER nouvel_utilisateur;
-- Assignez un mot de passe à votre utilisateur :
ALTER USER nouvel_utilisateur WITH ENCRYPTED PASSWORD 'mon_mot_de_passe';
-- Quittez la console :
\q
```
```shell script
# Testons :
psql nouvelle_base # Une invite de commande psql s'ouvrira.

# Quittez l'invite
exit
# « Sortez » de l'utilisateur postgres.
exit
```