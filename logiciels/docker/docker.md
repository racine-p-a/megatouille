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