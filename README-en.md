## Table of Contents

* [The Build](#the-build)
  * [BIOS Settings](#bios-settings)
* [Prepare Install Media](#prepare-install-media)
* [Install the Bootloader](#install-the-bootloader)
* [Kernel Extensions](#kernel-extensions)
  * [Mandatory](#mandatory)
  * [Post Installation](#post-installation)
  * [Optional](#optional)
* [Partition Boot Drive](#partition-boot-drive)
* [Video Demonstrations](#video-demonstrations)
* [Compatibility](#compatibility)
* [Releases](#releases)
* [License](#license)
* [Warranty](#warranty)
* [Download](#download)

## The Build
View the complete [specs](https://www.dualbootpc.com/systems/desktop/790sff/) at `http://gixxer.us/2nEq9tY`

## Prepare Install Media
1. Download the installer for [macOS High Sierra](https://www.dualbootpc.com/software/system/macos/high-sierra/) from the Mac App Store.
2. Open Terminal and format the target 16 GB [USB drive](https://www.dualbootpc.com/hardware/usb/) with the following command:

    `diskutil partitionDisk /dev/{DISK_ID} GPT JHFS+ "HighSierraUSB" 100%` 
    
3. Partition the 16 GB [USB drive](https://www.dualbootpc.com/hardware/usb/) and give 12 GB to the **HighSierraUSB** and 4 GB to **Post Installation**.
4. [Create the bootable macOS installer](https://www.dualbootpc.com/guide/creating-a-usb-installer/): Works for [OS X Mavericks](https://www.dualbootpc.com/software/system/macos/mavericks/) through [macOS Big Sur](https://www.dualbootpc.com/software/system/macos/big-sur/).

    `sudo /Applications/Install\ macOS\ High\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/HighSierraUSB --applicationpath /Applications/Install\ macOS\ High\ Sierra.app`
5. Once the program finishes in the Terminal, your [USB drive](https://www.dualbootpc.com/hardware/usb/) will be called the following:

    `Install macOS High Sierra`

## Install the Bootloader
**USB Flash Drive**
* Download the [Clover](https://www.dualbootpc.com/software/bootloader/clover/) 2.4k r4934 installer.
* Install [Clover](https://www.dualbootpc.com/software/bootloader/clover/) 2.4k r4934 to your 16 GB [USB drive](https://www.dualbootpc.com/hardware/usb/) device and customize with the following options:
  * Clover for Legacy booting
    * Mandatory drivers
      * ApfsDriverLoader-64.efi
      * AptioMemoryFix-64.efi
      * HFSPlus.efi
    * Recommended drivers
      * AudioDxe-64.efi ([Enables boot sound](https://github.com/Sipylus/Dell-OptiPlex-790/issues/1) in compatible themes)
      * NvmExpress-64.efi (Enabled The Detection of the NVMe drive)

**Boot Drive**
* Export the **BOOT** and the **CLOVER** from the EFI Folder on the USB Flash Drive and import to the EFI Folder on the boot drive.
* Install [Clover](https://www.dualbootpc.com/software/bootloader/clover/) v2.4k r4934 to your boot drive and customize with the **additional** options:
  * Install RC Scripts in target volume
  * Install Clover Preference Pane (Select during Post Installation)
* Eject all USB Flash Drives and restart to the BIOS.
* Set the boot drive with Clover in the ESP as the Primary and exit.

## Kernel Extensions
### [Mandatory](https://github.com/nyhtml/KEANU)
  * FakeSMC.kext (This will be swapped to VirtualSMC.kext in future [releases](https://github.com/Sipylus/Dell-OptiPlex-790/releases) for future support of macOS Big Sur.)
  * Lili.kext
  * WhateverGreen.kext

### [Post Installation](https://github.com/nyhtml/KEANU)
  * AppleALC.kext
  * IntelMausiEthernet.kext (This will be swapped to IntelMausi.kext in future [releases](https://github.com/Sipylus/Dell-OptiPlex-790/releases) for future support of macOS Big Sur.)
  * USBInjectAll.kext
  * XHCI-200-series-injector.kext

### [Optional](https://github.com/nyhtml/KEANU)
  * CPUFriend.kext
  * RealtekRTL8111.kext (PCI-e Wi-Fi)
  * RtWlanU.kext (USB Wi-Fi)
  * RtWlanU1827.kext (USB Wi-Fi)

View the list of [kexts](https://www.dualbootpc.com/software/kexts/) available on GixxerPC: `http://gixxer.us/3aS5d6m`

## Partition Boot Drive
  * EFI 200MB - FAT32
  * Win 400GB - NTFS
  * Ubuntu - 100GB - EXT4
  * macOS - 500GB - NTFS

Note: Example above is for a Triple Boot 1TB/100GB Drive. Adjust or drop partitions to match your drive.

## Video Demonstrations
  * [GixxerPC.com](https://www.gixxerpc.com/systems/desktop/790sff/demos/)
  * [VideoHooligan.com](https://www.videohooligan.com)

## Compatibility<br>
The latest <a href="https://github.com/Sipylus/OS">Operating System</a> that is supported is Catalina 10.15.7.
* macOS
  * [macOS Monterey](https://www.dualbootpc.com/software/system/macos/monterey/) (undergoing testing)
  * [macOS Big Sur](https://www.dualbootpc.com/software/system/macos/big-sur/) (undergoing testing)
  * [macOS Catalina](https://www.dualbootpc.com/software/system/macos/mojave/)
  * [macOS Mojave](https://www.dualbootpc.com/software/system/macos/mojave/)
  * [macOS High Sierra](https://www.dualbootpc.com/software/system/macos/high-sierra/) 
  * [macOS Sierra](https://www.dualbootpc.com/software/system/macos/sierra/)
* Ubuntu
  * [Ubuntu Desktop](https://www.dualbootpc.com/software/system/ubuntu/desktop/)
* Windows
  * [Windows 11](https://www.dualbootpc.com/software/system/windows/eleven/) (undergoing testing)
  * [Windows 10](https://www.dualbootpc.com/software/system/windows/ten/) 
  * [Windows 8](https://www.dualbootpc.com/software/system/windows/eight/)
  * [Windows 7](https://www.dualbootpc.com/software/system/windows/seven/)

## Releases
**Warning**: Our [releases](https://github.com/Sipylus/Dell-OptiPlex-790/releases/) are configured to work with systems configured with similar [specs](https://www.dualbootpc.com/systems/desktop/790sff/).

## Warranty
THIS [Dell OPTIPLEX 790 SFF](https://github.com/Sipylus/Dell-OptiPlex-790) REPO IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR<br>
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,<br>
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE<br>
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER<br>
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,<br>
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE<br>
SOFTWARE.

## Download
[Download](https://github.com/Sipylus/Dell-OptiPlex-790/releases/latest/download/EFI.zip) or view the [releases](https://github.com/Sipylus/Dell-OptiPlex-790/releases/) on GitHub.
