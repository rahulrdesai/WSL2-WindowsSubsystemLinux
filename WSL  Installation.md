#WSL2 - Installation


**Windows 11**
1. Launch Windows Terminal/Powershell
2. Type the command 'wsl --install --no-distribution --web-download'. This command will install the WSL2 kernel from the Microsoft server instead of the Windows Store. This enables WSL to be updated via Microsoft Updates which gets the updates quicker than the store app.
3. Reboot the system.
4. After reboot launch terminal/powershell again. Run the command 'wsl --status'. It should display the WSL version which means WSL was installed.
5. Run the command 'wsl --list --online'. This will list all the available Linux distributions available for WSL.
6. You can also install your preferred distro from the Microsoft Store. To install your preferred distro from command line type the command 'wsl --install <distro name> --web-download'. The name is no case sensitive. This will download and install the distro from the web instead of the Microsoft Store.
7. Once installed it will ask you to supply a username and password. Store this safely. It wont always ask you but will be needed when you install a package or perform other activities that require Superuser rights in the linux distro.
    
Optionally if you want WSL1 support on Windows 11 then enable the Windows Subsystem for Linux component by running the below command
    `dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart`

    
**Windows 10**

NOTE: You need Windows 10 Build 2004 or higher. Build 20H2 recommended.

Reference Links:

    WSL:
    https://docs.microsoft.com/en-us/windows/wsl/install-win10#step-4---download-the-linux-kernel-update-package
    https://docs.microsoft.com/en-us/windows/wsl/
    

1. RUN POWERSHELL as administrator and run the below command
`Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux`
1. Reboot windows
1. Run powershell again as administrator and run the 2 commands below
`dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart`
`dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart`
1. Reboot windows
1. Now to upgrade to WSL2 download the latest Linux Kernel from the Microsoft website: [https://aka.ms/wsl2kernel​]()
1. Install the downloaded file and reboot windows.
1. Now we need to set the default version of WSL to v2. Run powershell as admin again and run the below command
`wsl --set-default-version 2`
1. Check that the version is set to v2
`wsl --list --verbose`

#Running default Bash
1. Click on the start menu and search for Bash
1. Open the Bash application to launch the WSL
1. This is the default linux kerne that is installed with WSL. You can run basic linux tasks using this.

#Optional - Windows Terminal app
1. The windows terminal app is an official release from Microsoft and available on the Microsoft Store.
1. The windows terminal app is a multipurpose app that can open various terminals like CMD, Powershell, WSL and even Bash in tab style layout.
1. Its a good app to open multiple WSL terminals and Powershell in tabs in a single app without cluttering the taskbar.

