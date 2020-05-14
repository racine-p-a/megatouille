# Markdown

## Écrire une liste imbriquée

**_Le code :_**

```markdown
+ Logiciels
  - Vidéo
    * VLC
      1. Vidéo en réseau
    * Blender
      1. Faire des vidéos
  - Audio
    * Amarok
      1. Faire sa playlist
        + Différentes playlists
    * Totem
    * VLC
```

**_Son résultat :_**

+ Logiciels
  - Vidéo
    * VLC
      1. Vidéo en réseau
    * Blender
      1. Faire des vidéos
  - Audio
    * Amarok
      1. Faire sa playlist
        + Différentes playlists
    * Totem
    * VLC

## Faire un tableau

```markdown
En-tête 1 | En-tête 2 | En-tête 3
--------- | --------- | ---------
case 1 | case 2 | case 3
1|2|3
```


En-tête 1 | En-tête 2 | En-tête 3
--------- | --------- | ---------
case 1 | case 2 | case 3
1|2|3


## Règles sur les liens internes

Un lien se fait sur un titre, quelque soit son importance. Les règles (trouvées de manière empirique) semblent être :

- tout le texte est mis en minuscule
- suppression simple des caractères : ?'!.
- remplacement des espaces par des tirets (y compris si le caractère suivant a été supprimé)
- les diacritiques françaises semblent gardées (éàè...)
- les diacritiques majuscules (ÉÇ...) sont simplement gardées telles quelles également, minifiez-les aussi au cas où.

```markdown
## Étrange ça va moi, et vous? Ça peut surprendre ! je vous assure.
``` 

sera accessible par ce lien :

```markdown
url/de/la/page#étrange-ça-va-moi-et-vous-Ça-peut-surprendre--je-vous-assure
```
