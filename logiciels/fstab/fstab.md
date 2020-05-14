# fstab

## Monter automatiquement un disque au démarrage

```shell script
# Créons le point de montage, la où apparaîtra le disque une fois monté.
sudo mkdir /media/HDDLinux
# Affichons la liste des disques durs.
sudo blkid
```

Cela vous donnera une réponse de type :

```shell script
/dev/mapper/vgkubuntu-root: UUID="a2135d1a-2e4f-4ece-b3a1-e5861f93caf0" TYPE="ext4"
/dev/sdb1: LABEL="HDDWindows" UUID="6A65A8295AEB5A9B" TYPE="ntfs" PTTYPE="atari" PARTUUID="8096b532-01"
/dev/sda1: UUID="8F47-FAEA" TYPE="vfat" PARTUUID="5496b801-01"
/dev/sda5: UUID="Vrinnu-9SeQ-vfCH-bdth-RVle-gl3E-d53NTs" TYPE="LVM2_member" PARTUUID="5496b801-05"
/dev/sdd1: LABEL="RM-CM-)cupM-CM-)ration" UUID="4606EE7606EE6681" TYPE="ntfs" PARTLABEL="Basic data partition" PARTUUID="0eb61bc9-e1b7-452d-9966-31a56658c31d"
/dev/sdd2: UUID="78F1-68BC" TYPE="vfat" PARTLABEL="EFI system partition" PARTUUID="6a1ffe56-bd80-42b1-9039-7d5c8017be03"
/dev/sdd3: PARTLABEL="Microsoft reserved partition" PARTUUID="69796955-6fa6-4799-bb96-80655aff4473"
/dev/sdd4: UUID="3610FD1D10FCE4B1" TYPE="ntfs" PARTLABEL="Basic data partition" PARTUUID="327fc2bc-6673-4505-9018-2cf553953195"
/dev/sdc1: LABEL="HDDLinux" UUID="bc8e7cda-1b66-4c69-a5e6-c3203aa32e59" TYPE="ext4" PARTUUID="dcaba15d-ef1a-472e-9c87-2cfec09a9aca"
/dev/mapper/vgkubuntu-swap_1: UUID="441319c8-a32a-4de2-9bd1-cc116f57d59a" TYPE="swap"
```

Chaque ligne correspond à l'un de vos disques durs. Trouvez celui que vous
souhaitez monter à chaque démarrage. Prenons, par exemple, l'avant-dernière
ligne : le disque « HDDLinux » avec un UUID _bc8e7cda-1b66-4c69-a5e6-c3203aa32e59_.

```shell script
# OUvrez le fichier fstab :
sudo nano /etc/fstab
```

Il ne vous reste plus qu'à insérer une ligne à la fin du fichier. Notez que
les informations sur une même ligne doivent être séparées par une tabulation.
Vous pouvez également metttre des commentaires en les précédant d'un
croisillon (#).

Dans notre cas, nous ajouterons ceci :
```shell script
# Montage automatique du disque nommé HDDLinux :
UUID=bc8e7cda-1b66-4c69-a5e6-c3203aa32e59 /media/HDDLinux ext4  defaults  0 2
```

Avec dans l'ordre :
1. UUID du disque
1. Point de montage du disque
1. Format du disque (NTFS, ext4, FAT32, ...)
1. Les options générales (laissez à _defaults_ à moins d'avoir une idée bien précise)
1. Les options de sauvegardes (laissez à _0_)
1. Les options de tests de sauvegardes (0 pour swap/windows, 1 pour partition principale, 2 pour les autres partitions linux)


Voir la [doc-ubuntu](https://doc.ubuntu-fr.org/mount_fstab) pour des infos
compléùentaires.