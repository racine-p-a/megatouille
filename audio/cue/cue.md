# Fichiers .cue

## Séparer un album flac+cue

Certains albums sont parfois faits d'un seul fichier `.flac` accompagné d'un autre fichier `.cue` qui sert à en borner
les différentes pistes.

Pour séparer le fichier `.flac` proprement en plusieurs morceaux suivant les informations du fichier `.cue`, il est
nécessaire d'utiliser un outil dédié : `shnsplit`.

```bash
# Installation du logiciel (vient des dépôts UBUNTU officiels)
sudo apt install cuetools shntool flac

# Découpage de votre fichier
shnsplit -f fichier.cue -t %n-%t -o flac fichier.flac
```