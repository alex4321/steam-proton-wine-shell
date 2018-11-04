Description
-----------
This is script which'll simplify running shell with Wine prefix created by Steam Proton.

It depends from next software:
- bash
- curl
- dialog

Can be installed (in Ubuntu 18.04) next way:
```
sudo apt install curl dialog
```

Usage
-----
For example, I have Ubuntu 18.04 and my steam library in ```/mnt/hdd/SteamLibrary```.
You can specify library as first param, in other cases script'll scan all mount points and ```$HOME``` for ```SteamLibrary``` directory.
For example, to run Fallout 4 I need to install xact to wineprefix by winetricks and than - override xact imports in ```winecfg```.

The problem is that I'll need to manually found required wineprefix in ```/mnt/hdd/SteamLibrary/steamapps/compatdata/```, then search which Proton version it use and then - add both things to ```WINEPREFIX``` and ```PATH``` variables.
It's not a good idea.

With given script I'll just make next steps:
- run ```steam-proton-wine-shell```
- when it finishes with scanning library - it'll allow me to choose application which I want to configure
- I'll choose "Fallout 4"
- then it'll start bash shell prepared to work with right prefix and wine:
  ```
  alex4321@alex4321-Inspiron-15-7000-Gaming:/mnt/hdd/SteamLibrary/steamapps/compatdata/377160/pfx$ which wine
  /mnt/hdd/SteamLibrary/steamapps/common/Proton 3.16//dist/bin/wine
  alex4321@alex4321-Inspiron-15-7000-Gaming:/mnt/hdd/SteamLibrary/steamapps/compatdata/377160/pfx$ echo $WINEPREFIX
  /mnt/hdd/SteamLibrary/steamapps/compatdata/377160/pfx
  ```
