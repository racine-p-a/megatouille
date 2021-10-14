# Docker

## Images

### Afficher la liste de toutes les images docker présentes sur la machine

```bash
docker images -a
```

### Nettoyage des images docker inutilisées

```bash
docker system prune -a
```

## Conteneurs

```bash
# Liste des conteneurs
docker ps -a

# Suppression d'un conteneur
docker rm ID_or_Name
```

## Processus de création

Commencez par avoir un fichier `Dockerfile`. Une fois cela fait, vous pouvez bâtir l'image associée.

```bash
# Build d'une image docker. N'oubliez pas le point à la fin.
docker build -t nom_de_votre_image .
# L'argument -t assigne un tag à l'image créée (le .)
```