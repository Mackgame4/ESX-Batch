# ESX-Batch
A simple ESX Batch file to download esx and all the addons, why?, just to help users that can't make a default ESX server or a FiveM server and help people who need to download the esx and addons every new release, simply an **ESX one click installer**.

# :clipboard: **Source code**

```
@echo off
color 02
mode con:cols=154 lines=20
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
echo "                                            ________      ___    ___      _____ ______   ________  ________  ___  __                                   ";
echo "                                           |\   __  \    |\  \  /  /|    |\   _ \  _   \|\   __  \|\   ____\|\  \|\  \                                 ";
echo "                                           \ \  \|\ /_   \ \  \/  / /    \ \  \\\__\ \  \ \  \|\  \ \  \___|\ \  \/  /|_                               ";
echo "                                            \ \   __  \   \ \    / /      \ \  \\|__| \  \ \   __  \ \  \    \ \   ___  \                              ";
echo "                                             \ \  \|\  \   \/  /  /        \ \  \    \ \  \ \  \ \  \ \  \____\ \  \\ \  \                             ";
echo "                                              \ \_______\__/  / /           \ \__\    \ \__\ \__\ \__\ \_______\ \__\\ \__\                            ";
echo "                                               \|_______|\___/ /             \|__|     \|__|\|__|\|__|\|_______|\|__| \|__|                            ";
echo "                                                        \|___|/                                                                                        ";

:choice
set /P c=----------------------------------------------------------Already have Git and WGET [Y/N]?----------------------------------------------------------------
if /I "%c%" EQU "Y" goto :version
if /I "%c%" EQU "N" goto :git
goto :choice

:git
start https://git-scm.com/download/win
start https://builtvisible.com/download-your-website-with-wget
goto :version

:version
set /P c=-------------------------------------------------------------- 1-ESX V1 / 2-ESX V2 [1/2]?-----------------------------------------------------------------
if /I "%c%" EQU "1" goto :old-esx
if /I "%c%" EQU "2" goto :new-esx

:old-esx
mkdir ESX
cd ESX
wget https://runtime.fivem.net/artifacts/fivem/build_server_windows/master/3352-2222c06a36a89286edb9fc45fdc2f62d4a548ead/server.zip
git clone https://github.com/citizenfx/cfx-server-data
rename "cfx-server-data" "server-data"
cd server-data
wget https://pastebin.com/raw/qT3vZqyj
rename "qT3vZqyj" "server.cfg"
wget https://i.imgur.com/irymu1U.png
rename "irymu1U.png" "logo.png"
cd resources
mkdir [essentials]
cd [essentials]
git clone https://github.com/esx-framework/es_extended/archive/v1-final.zip
git clone https://github.com/brouznouf/fivem-mysql-async
rename "fivem-mysql-async" "mysql-async"
git clone https://github.com/esx-framework/async
git clone https://github.com/esx-framework/skinchanger
git clone https://github.com/esx-framework/cron
cd ..
mkdir [esx]
cd [esx]
git clone https://github.com/esx-framework/esx_holdup
git clone https://github.com/esx-framework/esx_jobs
git clone https://github.com/esx-framework/esx_optionalneeds
git clone https://github.com/esx-framework/esx_rpchat
git clone https://github.com/esx-framework/esx_datastore
git clone https://github.com/esx-framework/esx_joblisting
git clone https://github.com/esx-framework/esx_weaponshop
git clone https://github.com/esx-framework/esx_identity
git clone https://github.com/esx-framework/esx_shops
git clone https://github.com/esx-framework/esx_taxijob
git clone https://github.com/esx-framework/esx_phone
git clone https://github.com/esx-framework/esx_accessories
git clone https://github.com/esx-framework/esx_vehicleshop
git clone https://github.com/esx-framework/esx_skin
git clone https://github.com/esx-framework/instance
git clone https://github.com/esx-framework/esx_policejob
git clone https://github.com/esx-framework/esx_license
git clone https://github.com/esx-framework/esx_society
git clone https://github.com/esx-framework/esx_billing
git clone https://github.com/esx-framework/esx_addoninventory
git clone https://github.com/esx-framework/esx_addonaccount
git clone https://github.com/esx-framework/esx_realestateagentjob
git clone https://github.com/esx-framework/esx_whitelist
git clone https://github.com/esx-framework/esx_menu_list
git clone https://github.com/esx-framework/esx_menu_dialog
git clone https://github.com/esx-framework/esx_lscustom
git clone https://github.com/esx-framework/esx_bankerjob
git clone https://github.com/esx-framework/esx_barbershop
git clone https://github.com/esx-framework/esx_basicneeds
git clone https://github.com/esx-framework/esx_boat
git clone https://github.com/esx-framework/esx_ambulancejob
git clone https://github.com/esx-framework/esx_drugs
git clone https://github.com/esx-framework/esx_clotheshop
git clone https://github.com/esx-framework/esx_sit
git clone https://github.com/esx-framework/esx_property
git clone https://github.com/esx-framework/esx_status
git clone https://github.com/esx-framework/esx_dmvschool
git clone https://github.com/esx-framework/esx_atm
git clone https://github.com/esx-framework/esx_menu_default
git clone https://github.com/esx-framework/esx_service
git clone https://github.com/esx-framework/esx_boilerplate
git clone https://github.com/esx-framework/esx_migrate
git clone https://github.com/esx-framework/esx_cruisecontrol
git clone https://github.com/esx-framework/esx_animations
git clone https://github.com/esx-framework/esx_whitelistEnhanced
git clone https://github.com/esx-framework/esx_voice
git clone https://github.com/esx-framework/esx_garage
git clone https://github.com/esx-framework/esx_mechanicjob
goto :end

:new-esx
mkdir ESX
cd ESX
wget https://runtime.fivem.net/artifacts/fivem/build_server_windows/master/3352-2222c06a36a89286edb9fc45fdc2f62d4a548ead/server.zip
git clone https://github.com/citizenfx/cfx-server-data
rename "cfx-server-data" "server-data"
cd server-data
wget https://pastebin.com/raw/qT3vZqyj
rename "qT3vZqyj" "server.cfg"
wget https://i.imgur.com/irymu1U.png
rename "irymu1U.png" "logo.png"
cd resources
mkdir [esx]
cd [esx]
git clone https://github.com/esx-framework/es_extended
git clone https://github.com/brouznouf/fivem-mysql-async
rename "fivem-mysql-async" "mysql-async"
git clone https://github.com/esx-framework/async
git clone https://github.com/esx-framework/skinchanger
git clone https://github.com/esx-framework/cron
goto :end

:end
pause
start https://docs.fivem.net/docs/server-manual/setting-up-a-server/
exit
```

# :lock: **Requirements:**

***IMPORTANT:*** __Windows only__

[Git](https://git-scm.com)  
`Installing Git: Just download and follow the installer.`

[WGET](https://eternallybored.org/misc/wget)  
`Installing WGET:
Download the lastest version of WGET (for me 1.20.3), download the EXE, then copy and paste the EXE on your "C:\Windows\System32", carefully to do not destroy your PC, after that, it's done.`

# :gear: **How to Use**

- Download the **Requirements**
- Put ESX.bat in your Desktop
- Execute and answer questions
- Wait installation and have fun

# :bookmark: **Why batch?**
Because is more "users friendly" and more thrustable than a .exe or a compiled file

# :cloud: **Download:**

## [Here](https://github.com/Mackgame4/ESX-Batch) or Github (https://github.com/Mackgame4/ESX-Batch)
### [Join our Discord](https://discord.io/mack) or in (hhttps://discord.io/mack)
