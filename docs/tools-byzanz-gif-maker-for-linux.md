# Byzanz Gif Maker

Byzanz is an awesome tool for recording GIFs on Linux. It is light and gives an output directly to a gif file. The colors go off often, but the small file size makes up for it.

## Installing
(From [this AskUbuntu answer](http://askubuntu.com/questions/107726/how-to-create-animated-gif-images-of-a-screencast#answer-123515))

### 11.10 to 13.10

Unfortunately support has been dropped and you can no longer find any packages for Ubuntu that wont break your system and have missing unsatisfiable dependencies.

Fortunately Debian still maintains the package for Sid and the GIT repository still exists.

If you want to go ahead and install the .deb file from Sid (works in Ubuntu 11.10, just tested, no warranties!), download it from the Debian packages page and install it with sudo dpkg -i.

Also, one of our esteemed moderators has ported the Debian package to a PPA making it easier to install, you can add it to your system and install Byzanz by opening a terminal and typing

    sudo add-apt-repository ppa:fossfreedom/byzanz
    sudo apt-get update && sudo apt-get install byzanz

### 14.04 and above

Byzanz is now available from the universe repository

    sudo apt-get install byzanz


## Usage

Usage directly from the package requires a lot of parameters and argument typing in the terminal. However, a great fellow went ahead and made a script to make it easy and added GUI features to it.

(From [this AskUbuntu answer](http://askubuntu.com/questions/107726/how-to-create-animated-gif-images-of-a-screencast#answer-201018))

+ Add [this script](https://gist.github.com/nihal111/c52539a52d1b88335d86db9e4ba77663) to the $PATH of your Linux (`/usr/bin/` would work).
+ Save the script as `byzanz-record-window` and run `sudo chmod +x byzanz-record-window` inside that directory to grant execution permission to the script.
+ Run the script from the terminal as easily as calling out `byzanz-record-window`.
+ You can change the delay and other default values by editing the script.