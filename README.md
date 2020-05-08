# ESX-Batch
A simple ESX Batch file to download esx and all the addons

![image.png](https://i.imgur.com/cezc10o.png)
# :clipboard: **Source code**

```
@echo off
color 02
mode con:cols=154 lines=19
echo " _______   ________       ___    ___      ________  ________  ___       __   ________   ___       ________  ________  ________  _______   ________     ";
echo "|\  ___ \ |\   ____\     |\  \  /  /|    |\   ___ \|\   __  \|\  \     |\  \|\   ___  \|\  \     |\   __  \|\   __  \|\   ___ \|\  ___ \ |\   __  \    ";
echo "\ \   __/|\ \  \___|_    \ \  \/  / /    \ \  \_|\ \ \  \|\  \ \  \    \ \  \ \  \\ \  \ \  \    \ \  \|\  \ \  \|\  \ \  \_|\ \ \   __/|\ \  \|\  \   ";
echo " \ \  \_|/_\ \_____  \    \ \    / /      \ \  \ \\ \ \  \\\  \ \  \  __\ \  \ \  \\ \  \ \  \    \ \  \\\  \ \   __  \ \  \ \\ \ \  \_|/_\ \   _  _\  ";
echo "  \ \  \_|\ \|____|\  \    /     \/        \ \  \_\\ \ \  \\\  \ \  \|\__\_\  \ \  \\ \  \ \  \____\ \  \\\  \ \  \ \  \ \  \_\\ \ \  \_|\ \ \  \\  \| ";
echo "   \ \_______\____\_\  \  /  /\   \         \ \_______\ \_______\ \____________\ \__\\ \__\ \_______\ \_______\ \__\ \__\ \_______\ \_______\ \__\\ _\ ";
echo "    \|_______|\_________\/__/ /\ __\         \|_______|\|_______|\|____________|\|__| \|__|\|_______|\|_______|\|__|\|__|\|_______|\|_______|\|__|\|__|";
echo "             \|_________||__|/ \|__|                                                                                                                   ";
echo "                                                                                                                                                       ";
echo "                                                                                                                                                       ";
echo "                                                  ________      ___    ___      ________  _____ ______   ________                                      ";
echo "                                                 |\   __  \    |\  \  /  /|    |\   __  \|\   _ \  _   \|\   ____\                                     ";
echo "                                                 \ \  \|\ /_   \ \  \/  / /    \ \  \|\  \ \  \\\__\ \  \ \  \___|                                     ";
echo "                                                  \ \   __  \   \ \    / /      \ \  \\\  \ \  \\|__| \  \ \  \  ___                                   ";
echo "                                                   \ \  \|\  \   \/  /  /        \ \  \\\  \ \  \    \ \  \ \  \|\  \                                  ";
echo "                                                    \ \_______\__/  / /           \ \_______\ \__\    \ \__\ \_______\                                 ";
echo "                                                     \|_______|\___/ /             \|_______|\|__|     \|__|\|_______|                                 ";
echo "                                                              \|___|/                                                                                  ";

:choice
set /P c=--------------------------------------------------------------Already have Git [Y/N]?---------------------------------------------------------------------
if /I "%c%" EQU "Y" goto :version
if /I "%c%" EQU "N" goto :git
goto :choice

:git
start https://git-scm.com/download/win
start https://builtvisible.com/download-your-website-with-wget/
goto :version

:version
set /P c=-------------------------------------------------------------- 1-Old ESX / 2-New ESX [1/2]?---------------------------------------------------------------
if /I "%c%" EQU "1" goto :old-esx
if /I "%c%" EQU "2" goto :new-esx

:old-esx
mkdir ESX
cd ESX
wget https://runtime.fivem.net/artifacts/fivem/build_server_windows/master/2445-618f12641672275983a0d84c087d50a32ab7fefc/server.zip
git clone https://github.com/citizenfx/cfx-server-data
rename "cfx-server-data" "server-data"
cd server-data
wget https://pastebin.com/raw/9pPPUDFU
rename "9pPPUDFU" "server.cfg"
wget https://i.imgur.com/irymu1U.png
rename "irymu1U.png" "logo.png"
cd resources
mkdir [essentials]
cd [essentials]
git clone https://github.com/kanersps/essentialmode
git clone https://github.com/ESX-Org/es_extended/archive/1.1.0.zip
git clone https://github.com/brouznouf/fivem-mysql-async
rename "fivem-mysql-async" "mysql-async"
git clone https://github.com/ESX-Org/async
git clone https://github.com/kanersps/esplugin_mysql
git clone https://github.com/kanersps/es_ui
git clone https://github.com/kanersps/es_admin
rename "es_admin" "es_admin2"
git clone https://github.com/blattersturm/fxmigrant
git clone https://github.com/ESX-Org/skinchanger
git clone https://github.com/ESX-Org/cron
cd ..
mkdir [esx]
cd [esx]
git clone https://github.com/ESX-Org/esx_holdup
git clone https://github.com/ESX-Org/esx_jobs
git clone https://github.com/ESX-Org/esx_optionalneeds
git clone https://github.com/ESX-Org/esx_rpchat
git clone https://github.com/ESX-Org/esx_datastore
git clone https://github.com/ESX-Org/esx_joblisting
git clone https://github.com/ESX-Org/esx_weaponshop
git clone https://github.com/ESX-Org/esx_identity
git clone https://github.com/ESX-Org/esx_shops
git clone https://github.com/ESX-Org/esx_taxijob
git clone https://github.com/ESX-Org/esx_phone
git clone https://github.com/ESX-Org/esx_accessories
git clone https://github.com/ESX-Org/esx_vehicleshop
git clone https://github.com/ESX-Org/esx_skin
git clone https://github.com/ESX-Org/instance
git clone https://github.com/ESX-Org/esx_policejob
git clone https://github.com/ESX-Org/esx_license
git clone https://github.com/ESX-Org/esx_society
git clone https://github.com/ESX-Org/esx_billing
git clone https://github.com/ESX-Org/esx_addoninventory
git clone https://github.com/ESX-Org/esx_addonaccount
git clone https://github.com/ESX-Org/esx_realestateagentjob
git clone https://github.com/ESX-Org/esx_whitelist
git clone https://github.com/ESX-Org/esx_menu_list
git clone https://github.com/ESX-Org/esx_menu_dialog
git clone https://github.com/ESX-Org/esx_lscustom
git clone https://github.com/ESX-Org/esx_bankerjob
git clone https://github.com/ESX-Org/esx_barbershop
git clone https://github.com/ESX-Org/esx_basicneeds
git clone https://github.com/ESX-Org/esx_boat
git clone https://github.com/ESX-Org/esx_ambulancejob
git clone https://github.com/ESX-Org/esx_drugs
git clone https://github.com/ESX-Org/esx_clotheshop
git clone https://github.com/ESX-Org/esx_sit
git clone https://github.com/ESX-Org/esx_property
git clone https://github.com/ESX-Org/esx_status
git clone https://github.com/ESX-Org/esx_dmvschool
git clone https://github.com/ESX-Org/esx_atm
git clone https://github.com/ESX-Org/esx_menu_default
git clone https://github.com/ESX-Org/esx_service
git clone https://github.com/ESX-Org/esx_boilerplate
git clone https://github.com/ESX-Org/esx_migrate
git clone https://github.com/ESX-Org/esx_cruisecontrol
git clone https://github.com/ESX-Org/esx_animations
git clone https://github.com/ESX-Org/esx_whitelistEnhanced
git clone https://github.com/ESX-Org/esx_voice
git clone https://github.com/ESX-Org/esx_garage
git clone https://github.com/ESX-Org/esx_mechanicjob
goto :end

:new-esx
mkdir ESX
cd ESX
wget https://runtime.fivem.net/artifacts/fivem/build_server_windows/master/2445-618f12641672275983a0d84c087d50a32ab7fefc/server.zip
git clone https://github.com/citizenfx/cfx-server-data
rename "cfx-server-data" "server-data"
cd server-data
wget https://pastebin.com/raw/RjbBJUK9
rename "RjbBJUK9" "server.cfg"
wget https://i.imgur.com/irymu1U.png
rename "irymu1U.png" "logo.png"
cd resources
mkdir [essentials]
cd [essentials]
git clone https://github.com/ESX-Org/es_extended
git clone https://github.com/brouznouf/fivem-mysql-async
rename "fivem-mysql-async" "mysql-async"
git clone https://github.com/ESX-Org/async
git clone https://github.com/ESX-Org/skinchanger
git clone https://github.com/ESX-Org/cron
cd ..
mkdir [esx]
cd [esx]
git clone https://github.com/ESX-Org/esx_holdup
git clone https://github.com/ESX-Org/esx_jobs
git clone https://github.com/ESX-Org/esx_optionalneeds
git clone https://github.com/ESX-Org/esx_rpchat
git clone https://github.com/ESX-Org/esx_datastore
git clone https://github.com/ESX-Org/esx_joblisting
git clone https://github.com/ESX-Org/esx_weaponshop
git clone https://github.com/ESX-Org/esx_identity
git clone https://github.com/ESX-Org/esx_shops
git clone https://github.com/ESX-Org/esx_taxijob
git clone https://github.com/ESX-Org/esx_phone
git clone https://github.com/ESX-Org/esx_accessories
git clone https://github.com/ESX-Org/esx_vehicleshop
git clone https://github.com/ESX-Org/esx_skin
git clone https://github.com/ESX-Org/instance
git clone https://github.com/ESX-Org/esx_policejob
git clone https://github.com/ESX-Org/esx_license
git clone https://github.com/ESX-Org/esx_society
git clone https://github.com/ESX-Org/esx_billing
git clone https://github.com/ESX-Org/esx_addoninventory
git clone https://github.com/ESX-Org/esx_addonaccount
git clone https://github.com/ESX-Org/esx_realestateagentjob
git clone https://github.com/ESX-Org/esx_whitelist
git clone https://github.com/ESX-Org/esx_menu_list
git clone https://github.com/ESX-Org/esx_menu_dialog
git clone https://github.com/ESX-Org/esx_lscustom
git clone https://github.com/ESX-Org/esx_bankerjob
git clone https://github.com/ESX-Org/esx_barbershop
git clone https://github.com/ESX-Org/esx_basicneeds
git clone https://github.com/ESX-Org/esx_boat
git clone https://github.com/ESX-Org/esx_ambulancejob
git clone https://github.com/ESX-Org/esx_drugs
git clone https://github.com/ESX-Org/esx_clotheshop
git clone https://github.com/ESX-Org/esx_sit
git clone https://github.com/ESX-Org/esx_property
git clone https://github.com/ESX-Org/esx_status
git clone https://github.com/ESX-Org/esx_dmvschool
git clone https://github.com/ESX-Org/esx_atm
git clone https://github.com/ESX-Org/esx_menu_default
git clone https://github.com/ESX-Org/esx_service
git clone https://github.com/ESX-Org/esx_boilerplate
git clone https://github.com/ESX-Org/esx_migrate
git clone https://github.com/ESX-Org/esx_cruisecontrol
git clone https://github.com/ESX-Org/esx_animations
git clone https://github.com/ESX-Org/esx_whitelistEnhanced
git clone https://github.com/ESX-Org/esx_voice
git clone https://github.com/ESX-Org/esx_garage
git clone https://github.com/ESX-Org/esx_mechanicjob
goto :end

:end
pause
start https://docs.fivem.net/docs/server-manual/setting-up-a-server/
exit
```

# :lock: **Requirements:**

***IMPORTANT:*** Windows only

Git [https://git-scm.com/]

WGET [https://builtvisible.com/download-your-website-with-wget] or is using Windows server you dont need that

# :gear: **How to Use**

- Download the **Requirements**
- Put ESX.bat in your Desktop
- Execute and awser questions
- Wait installation and have fun
- Add to your server cfg the following line:

# :bookmark: **Why batch?**
Because is more "users friendly" and more thrustable than a .exe

# :cloud: **Download:**

## [Here](https://github.com/Dev-OMG/ESX-Batch) or Github (https://github.com/Dev-OMG/ESX-Batch)
### [Join ESX Discord](https://discord.gg/3R36mdX) or in (https://discord.gg/3R36mdX)
