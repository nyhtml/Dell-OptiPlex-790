#  :fox_face: Dell OptiPlex 790<br>
Dell OptiPlex 790 Hackintosh Desktop

## Table of Contents

* [The Build](#the-build)
  * [BIOS Settings](#bios-settings)
* [Prepare Install Media](#prepare-install-media)
* [Install the Bootloader](#install-the-bootloader)
* [Kernel Extensions](#kernel-extensions)
* [Install to Boot Drive](#install-to-boot-drive)
* [Compatibility](#compatibility)
* [Releases](#releases)
* [License](#license)
* [Warranty](#warranty)

## The Build

## Prepare Install Media
1. Download the installer for [macOS High Sierra](https://www.dualbootpc.com/software/system/macos/high-sierra/) from the Mac App Store.
2. Open Terminal and format the target 16 GB [USB drive](https://www.dualbootpc.com/hardware/usb/) with the following command:

    `diskutil partitionDisk /dev/{DISK_ID} GPT JHFS+ "HighSierraUSB" 100%` 
    
3. Partition the 16 GB [USB drive](https://www.dualbootpc.com/hardware/usb/) and give 12 GB to the **HighSierraUSB** and 4 GB to **Post Installation**.
4. [Create the bootable macOS installer](https://www.dualbootpc.com/guide/creating-a-usb-installer/): Works for [OS X Mavericks](https://www.dualbootpc.com/software/system/macos/mavericks/) through [macOS Big Sur](https://www.dualbootpc.com/software/system/macos/big-sur/).

    `sudo /Applications/Install\ macOS\ High\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/HighSierraUSB --applicationpath /Applications/Install\ macOS\ High\ Sierra.app`
5. Once the program finishes in the Terminal, your [USB drive](https://www.dualbootpc.com/hardware/usb/) will be called the following:

    `Install macOS High Sierra`









<strong>Not Included</strong><br>
– Paper Manuals/Product Setup Guides<br>
– Audio Cables/Video Cables/Adapters<br>
– Operating System Recovery Media<br>
– Any Application/Drivers/Programs Not Stated<br>
– Any Accessories/Media Not Stated<br>
– Carrying Case/Protective Skin<br>
<br>
# Compatibility<br>
The latest <a href="https://github.com/Sipylus/OS">Operating System</a> that is supported is Catalina 10.15.7.

# Releases
**Warning**: Our <a href="https://github.com/Sipylus/Dell-OptiPlex-790/releases">releases</a> are configured to work with systems configured with similar hardware.
