# Steam

## Astuces

## Récupérer les captures d'écran de steam

Pour récupérer les captures d'écran faites en jeu, il faut aller dans le dossier :
```text
/home/[username]/.steam/debian-installation/userdata/[steam_id3]/760/remote/[game_id]/screenshots
```
Dans le chemin ci-dessus, pensez à changer votre nom d'utilisateur (`[username]`),`[steam_id3]` qui
correspond à votre identifiant steamID3 ainsi que `[game_id]` qui correspond à l'identifiant du jeu en
question.
 

## Documentations variées

- [La ligne de commande steam](https://developer.valvesoftware.com/wiki/Command_Line_Options)
- [Steam Browser Protocol](https://developer.valvesoftware.com/wiki/Steam_browser_protocol)
- [SteamCMD](https://developer.valvesoftware.com/wiki/SteamCMD)

## Côté dév

### Lancer un jeu via la console linux

#### Lancer un jeu vanilla

```shell script
steam steam://rungameid/42960
```

#### Lancer un jeu steam avec des options de lancement

```shell script
steam steam://rungameid/42960//<args>/
```