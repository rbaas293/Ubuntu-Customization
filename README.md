# Ubuntu-Customization
This document provides instruction for setting up handy programs/tools for your new or existing Ubuntu install. 
## Folder Structure:
Make your Downloads folder structure, I did this:

      cd Downloads/
      mkdir programs    # Store all your downloaded packages/repositories in here


## Install atom text editor from GitHub:


      wget https://atom.io/download/deb # get atom-amd64.deb
      dpkg -i atom-amd64.deb # Install atom using dpkg:

Once atom is installed:
Install the atom IDE package from atoms package manager (apm):

      apm install atom-ide-ui
Install Language packs:

      apm install ide-cpp
      apm install ide-python

## Install libinput-tools
Enables Mac like swipe gestures for changing desktops.
Start with typing in the following command: 

      sudo gpasswd -a $USER input     # install will not work till you logout and then back in
Once you log back in:

      sudo apt-get install xdotool wmctrl     # These are dependency's
Install Base Tool:
Debian & Ubuntu:

      sudo apt-get install libinput-tools
Install libinput-gestures:

      git clone http://github.com/bulletmark/libinput-gestures
      cd libinput-gestures
      sudo ./libinput-gestures-setup install
Many users will be happy with the default configuration in which case you can just type the following and you are ready to go:
Start the process:

      libinput-gestures-setup start
Make the tool startup with Ubuntu:

      libinput-gestures-setup autostart

If this doesn't work for you then you will have to play around with the commands in ~/.config/ or aka /home/<yourusername>/.config/
to get there:

      cd home/<yourusername> | cd .config
or just simply type

      cd ~/.config
      sudo nano libinput-gestures.conf
and you want mac like swipe gestures for Ubuntu then,
copy the following into in ~/.config the libinput-gestures.conf file: aka your switching the keys to push, swipe up will be ctrl+alt+Down instead of ctrl+alt+Up

      #Example virtual desktop switching for Ubuntu Unity/Compiz. The
      # _internal command does not work for Compiz but you can explicitly
      # configure the swipe commands to work for a Compiz virtual 2
      # dimensional desktop as follows:
      gesture swipe up       xdotool key ctrl+alt+Down
      gesture swipe down     xdotool key ctrl+alt+Up
      gesture swipe left     xdotool key ctrl+alt+Right
      gesture swipe right    xdotool key ctrl+alt+Left">

FOR MORE INFO GO TO https://github.com/bulletmark/libinput-gestures



## OneDrive Client (Supports Office365)
*Reference: https://github.com/skilion/onedrive
Dependencies:

      sudo apt-get install libcurl4-openssl-dev
      sudo apt-get install libsqlite3-dev
      curl -fsS https://dlang.org/install.sh | bash -s dmd  #installs programing language "D"
      sudo wget http://master.dl.sourceforge.net/project/d-apt/files/d-apt.list -O /etc/apt/sources.list.d/d-apt.list
      wget -qO - http://dlang.org/d-keyring.gpg | sudo apt-key add -
      sudo apt-get update && sudo apt-get install dmd-bin
      sudo apt-get install dmd-bin             # yes do this again

Install:

      git clone https://github.com/skilion/onedrive.git
      cd onedrive
      make
      sudo make install

*Reference: https://github.com/skilion/onedrive

More: https://help.ubuntu.com/community/UsingTheTerminal

## Incremental history searching:

      cd Downloads/programs/
      gedit ~/.inputrc

Past the following and save:

      "\e[A": history-search-backward
      "\e[B": history-search-forward
      "\e[C": forward-char
      "\e[D": backward-char

To find a previous command is to enter say the first two or three letters and upward arrow will take you there quickly:

## Popcorn Time Install:
this is for the github clone, so far as not worked for me.
I suggest going to popcorntime.sh/ and downloading the .deb
then,
Install Popcorn Time:

      cd /opt/     # /opt is for "the installation of add-on application software packages"
      sudo git clone https://github.com/popcorn-official/popcorn-desktop.git     #Get official popcorn time repository.
      cd popcorn-desktop
      ./make_popcorn.sh
      sudo tar Jx -C /opt/popcorn-time      #Extract to directory made above
      sudo ln -sf /opt/popcorn-time/Popcorn-Time /usr/bin/popcorn-time      #create a symbolic link so non-privileged users can start Popcorn Time in any directory.
## Installing Vivialdi
Install:
* `wget https://downloads.vivaldi.com/stable/vivaldi-stable_1.12.955.48-1_amd64.deb`
* `dpkg -i vivaldi-stable_1.12.955.48-1_amd64.deb` 

To make flash player work with Vivaldi:

	sudo add-apt-repository "deb http://archive.canonical.com/ubuntu `lsb_release -cs` partner"
	sudo apt update
	sudo apt install adobe-flashplugin

## Desktop Customization Software:

	https://www.rainmeter.net/discover
	
## Glances (CLI System Monitoring)

Install:
* Run `sudo apt install glances`.
* or `curl -L https://raw.githubusercontent.com/nicolargo/glancesautoinstall/master/install.sh | sudo /bin/bash`.
* or `wget -O- https://raw.githubusercontent.com/nicolargo/glancesautoinstall/master/install.sh | sudo /bin/bash`.

Manual Installation:
```Bash
sudo apt-get install python-pip build-essential python-dev lm-sensors
sudo pip install psutil logutils bottle batinfo https://bitbucket.org/gleb_zhulik/py3sensors/get/tip.tar.gz zeroconf netifaces pymdstat influxdb elasticsearch potsdb statsd pystache docker-py pysnmp pika py-cpuinfo bernhard
sudo pip install glances
```	
More Info [Here](https://askubuntu.com/questions/293426/system-monitoring-tools-for-ubuntu).

## Foobix
Install Fooblnx in Ubuntu:
Stable:
sudo add-apt-repository ppa:foobnix-team/foobnix-player
sudo apt-get update
sudo apt-get install foobnix

Development:
sudo apt-get remove foobnix
sudo add-apt-repository ppa:popsul1993/ppa
sudo apt-get update
sudo apt-get install foobnix

Install from source:
sudo python setup.py install
# or
sudo make install
# or
./install

or if sudo apt-get install foobnix does not work and gives error "E: Package 'foobnix' has no installation candidate"

use: (will install all dependencies it can for the last run install package.)

	sudo apt-get -f install

if not go to <https://launchpad.net/~foobnix-team/+archive/ubuntu/foobnix-player/+packages>

find foobnix_<VERSION>_amd64.deb and copy link adress.

##
