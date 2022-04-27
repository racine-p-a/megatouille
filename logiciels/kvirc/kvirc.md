# Installer KVirc sur Ubuntu 20.04

Le code source est trouvable à trois endroits :
- en faisant un git clone du [dépôt](https://github.com/kvirc/KVIrc)
- sur la [page des releases](https://github.com/kvirc/KVIrc/releases)
- sur le [ftp](ftp://ftp.kvirc.net/pub/kvirc/5.0.0/source/KVIrc-5.0.0.tar.bz2) du [site](http://www.kvirc.net/?id=releases&platform=source&lang=fr)

```bash
# INSTALLER LES DÉPENDANCES
sudo apt install cmake gettext qt5-default libxmu-dev libxmu-headers freeglut3-dev libxext-dev libxi-dev libperl-dev qtmultimedia5-dev
# RÉCUPÉRER LE CODE SOURCE
wget ftp://ftp.kvirc.net/pub/kvirc/5.0.0/source/KVIrc-5.0.0.tar.bz2
# ÉTAPES DE COMPILATION
mkdir releases
cd releases
cmake .. # On peut ajouter des options comme indiqué dans la doc https://github.com/kvirc/KVIrc/wiki/installation#configure
sudo make install
```

Si le `sudo make install` pose problème, le [wiki](https://github.com/kvirc/KVIrc/wiki/FAQ#after-compiling-from-source-i-get-an-error-loading-the-libkvilib-shared-library-when-i-try-to-run-kvirc) propose plusieurs solutions dont celle-ci :
```bash
sudo -i
echo "/usr/local/lib" >> /etc/ld.so.conf
ldconfig
exit
sudo make install
```

Vous pouvez à présent installer KVirc 

