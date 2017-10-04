# Ubuntu Install Standards:

# Folder Structure:
Make your Downloads folder structure, I did this:
      cd Downloads/
      mkdir programs    # Store all your downloaded packages/repositories in here


# Install atom text editor from github:


      wget https://atom.io/download/deb # get atom-amd64.deb
      dpkg -i atom-amd64.deb # Install atom using dpkg:

Once atom is installed:
Install the atom IDE package from atoms package manager (apm):

      apm install atom-ide-ui
Install Language packs:

      apm install ide-cpp
      apm install ide-python

# Install libinput-tools

GNU nano 2.5.3                                                                 File: libinput-tools

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



# Another OneDrive Client!! (this one says it supports Office365)
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


More: https://help.ubuntu.com/community/UsingTheTerminal
///////////////////////////////////////////////////////////////
Incremental history searching:

      cd Downloads/programs/
      gedit ~/.inputrc

Past the following and save:
      
      "\e[A": history-search-backward
      "\e[B": history-search-forward
      "\e[C": forward-char
      "\e[D": backward-char

To find a previous command is to enter say the first two or three letters and upward arrow will take you there quickly:
/////////////////////////////////////////////////////////////// 
# Popcorn Time Install:
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












Desktop Customization Software:
https://www.rainmeter.net/discover
