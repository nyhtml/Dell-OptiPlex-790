#  :fox_face: Dell OptiPlex 790<br>
Dell OptiPlex 790 Hackintosh Desktop

## Table of Contents

* [The Build](#the-build)
  * [BIOS Settings](#bios-settings)
* [Prepare Install Media](#prepare-install-media)
* [Install the Bootloader](#install-the-bootloader)
* [Kernel Extensions](#kernel-extensions)
  * [Mandatory](#mandatory)
  * [Post Installation](#post-installation)
  * [Optional](#optional)
* [Install to Boot Drive](#install-to-boot-drive)
* [Compatibility](#compatibility)
* [Releases](#releases)
* [License](#license)
* [Warranty](#warranty)

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

## Kernel Extensions
### [Mandatory](https://github.com/nyhtml/KEANU)
  * FakeSMC.kext (This will be swapped in [Release X](https://github.com/Sipylus/Dell-OptiPlex-790/releases) for future support of macOS Big Sur.)
  * Lili.kext
  * WhateverGreen.kext

### [Post Installation](https://github.com/nyhtml/KEANU)
  * AppleALC.kext
  * IntelMausiEthernet.kext (This will be swapped in [Release X](https://github.com/Sipylus/Dell-OptiPlex-790/releases) for future support of macOS Big Sur.)
  * USBInjectAll.kext
  * XHCI-200-series-injector.kext

### [Optional](https://github.com/nyhtml/KEANU)
  * CPUFriend.kext
  * RealtekRTL8111.kext (PCI-e Wi-Fi)
  * RtWlanU.kext (USB Wi-Fi)
  * RtWlanU1827.kext (USB Wi-Fi)

View the list of [kexts](https://www.dualbootpc.com/software/kexts/) available on GixxerPC: `http://gixxer.us/3aS5d6m`

## Install to Boot Drive

## Compatibility<br>
The latest <a href="https://github.com/Sipylus/OS">Operating System</a> that is supported is Catalina 10.15.7.
* macOS
  * [macOS Montery](https://www.dualbootpc.com/software/system/macos/montery/) (undergoing testing)
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
**Warning**: Our <a href="https://github.com/Sipylus/Dell-OptiPlex-790/releases">releases</a> are configured to work with systems configured with similar hardware.

## Warranty
THIS [Dell OptiPlex 790 SFF](https://github.com/Sipylus/Dell-OptiPlex-790) REPO IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR<br>
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,<br>
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE<br>
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER<br>
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,<br>
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE<br>
SOFTWARE.
