# MacOSX-VM
==License violations==
According to the macOS and OS X software license agreement<ref>http://www.apple.com/legal/sla/</ref>, macOS should only be installed on Apple Mac devices. Neither the editors of this book nor Wikibooks have any liability over the installation of macOS or OS X guests on VirtualBox or any other violations of the software license.

This is against the EULA of Apple, and therefore following this article IS considered a violation of Apple's terms of service.

==Installation script==
The following installation script:
* ...is free and open-source
* ...requires only VirtualBox with its Extension Pack and dependencies that can be easily installed in a single command with most open-source package managers
* ...downloads macOS Catalina, Mojave and High Sierra directly from Apple's servers
* ...installs macOS without modifying the original Apple binaries and without third-party bootloaders
* ...creates a VM that is compatible with OpenCore and can be exported (with manual modifications) to KVM/QEMU for near-native performance
* ...runs on Linux, Windows (WSL, Cygwin), and macOS

[https://github.com/myspaghetti/macos-guest-virtualbox '''https://github.com/myspaghetti/macos-guest-virtualbox''' - Push-button installer of macOS on VirtualBox]

==Manual installation==
The manual installation requires access to the Mac App Store through an existing installation of macOS.

===Create ISO Installation Media===
# Download the macOS Installer file from the App Store<ref name=":0">https://support.apple.com/en-us/HT201475</ref> (OS X El Capitan and Sierra is downloadable from Apple's website).
# When download finishes, find the app, right-click and select "Show Package Contents".
# Inside the sub-folder Contents/SharedSupport you will find a InstallESD.dmg file.
# Open "Disk Utility"
# Choose Images > Convert
# In the window, choose the InstallESD.dmg to convert and the disk type to be "DVD/CD-R master for export". Also choose the name for installer disk and the final destination. Then click "Convert".
# After conversion completes, you will see a .cdr file in your destination folder.
# Open "Terminal"
# Enter <code>hdiutil convert -format UDTO -o /Your/Path/To/macOSInstaller.iso /Your/Path/To/YourCdrFile.cdr</code>
# Check destination folder. This is your file for installation in VirtualBox. There should be a .iso file extension.

===Installation in VirtualBox===
# Open VirtualBox. Click "new"
# Type the name for virtual machine and Mac OS X for type. Choose your version (if you have Mojave or Catalina, choose Mac OS X (64 bit)).
# Select memory size.
# Select "Create Virtual Disk Now"
# Choose VDI for format.
# Select storage name and size. The size should be at least 32 GB.
# Go to "Settings"
# Go to "Storage" Tab
# In the SATA controller, click "Add Optical Disk".
# Insert the .iso file.
# Go to "Display" tab.
# Set video memory to maximum value.
# Quit "Settings"
# Boot by clicking "Start".
# When it boots, you will see some data being displayed.
#
#This part needs clarification - UEFI Interactive Shell loads, but nothing happens. If you use the command "exit" you can shift to the EFI menu, but changing the settings doesn't seem to affect the progress of the UEFI Interactive Shell, which stops at the Shell> prompt. 
#
# After a while, you will need to choose the language for installation. Choose your own language.
# Then you will be asked where to install macOS.
# On the upper-left corner, you will see a "Utilities" button. Click it and select "Disk Utility".
# You will see a window with different storages on the left. Choose "VBOX HARDDISK Media". Note: You may have to select View/View All Devices
# Erase the Storage by clicking the "Erase" button on the top.
# You will be prompted to enter the name for the storage. Enter your desired name and continue.
# Wait for the process to complete. Then quit Disk Utility.
# You will find a new storage media, which is like a hard disk. Choose that storage for the installation of OS X to install.
# After installation completes, the virtual machine will automatically shut down. Go to "Settings".
# Go to the "Storage" section to eject the .iso file.
# Boot virtual machine again.
# Choose system language.
# Choose allow location or not.
# You will be asked to enter your Apple ID. Even if you have an Apple ID, <b>do not enter now</b>.
# Accept EULA of macOS.
# Restore Time Machine Backups (if you have)
# You will see the main page of OS X, open App Store.
# Enter your Apple ID and sign in...
<br>There should be 2 scenarios...
* Scenario 1: You will sign in within a short time. Congratulations! You have done it!
* Scenario 2: It took ages. Stop signing in and check the references below. <ref name=":0" />

== References ==

https://en.wikibooks.org/wiki/VirtualBox/Setting_up_a_Virtual_Machine/Mac_OS_X