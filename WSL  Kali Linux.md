## Kali Linux
Pre-requisite: WSL2 Should be installed. Please see previous article in this repo.
NOTE: It is important that you know how to operate Kali linux. The tools that get installed request for configuration info that one should have knowledge of. 

### Installation basic (Windows 11)
1. In powershell/terminal run the command 'wsl --install kali-linux --web-download
2. This will install the minimal version of Kali linux. Once installed it will ask you to create a username and password.
3. Once set run the command 'sudo apt update && sudo apt upgrade -y' to update all packages.
4. Now you can run either of the 2 below commands for the default or large version of Kali
   'sudo apt install -y kali-linux-default' OR
   'sudo apt install -y kali-linux-large'

### Installation (with RDP and seamless support)
Kali Linux supports GUI mode a new seamless mode which runs Kali GUI on top of your windows desktop.

Ref: https://www.kali.org/docs/wsl/win-kex/

Steps:
1. Search for Kali Linux in the store app,  click on get and install.
1. Once installed click on start menu and search for Kali. Click on the application to launch Kali Linux in its own bash terminal
1. Once installed we need to install a few components for GUI. Run the below commands:
- Update Kali
`sudo apt update && sudo apt upgrade -y`
- Install XFRCE Server for GUI
`sudo apt install kali-desktop-xfce -y`
- Install xRDP for remotin
`sudo apt install xrdp -y`
`sudo service xrdp start`
- Install dbus (required for GUI)
`sudo apt-get install -y dbus-x11`

### Kali - Commands to run GUI
 The below commands launch Kali in various modes (-s is sound support):
RDP: sudo kex --win -s
Enhanced: sudo kex --esm --ip -s
Seamless: sudo kex --sl -s

### Kali - Tshooting GUI/RDP
Every time you close the Kali bash terminal and re-open it the GUI/RDP stops working. The below commands fix that problem:
`sudo kex kill`
`sudo kex stop`

You can then run any of the commands to run the GUI either in RDP or seamless.

### Kali - Optional full upgrade
Kali for WSL is by default installed with limited packages. Run the below command to install all the packages.
`sudo apt install -y kali-linux-large`
