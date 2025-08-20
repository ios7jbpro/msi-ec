## ATTEMPT TO ADD SUPPORT FOR MSI CROSSHAIR 17 B12UGZ

Installation


Minimal kernel version is 6.5.0

Check version with uname -r

Install the following packages using the terminal:

For Debian: sudo apt install build-essential linux-headers-amd64

For Ubuntu: sudo apt install build-essential linux-headers-generic

For Fedora: sudo dnf install kernel-devel

For Arch: sudo pacman -S --needed base-devel linux-headers

Clone this repository and cd to it: git clone https://github.com/BeardOverflow/msi-ec && cd msi-ec

Choose one of the following installation methods

(Recommended) Installation using DKMS:

Verify that dkms is available: which dkms

Install the msi-ec kernel module: sudo make dkms-install

REBOOT

(Optional) To uninstall: sudo make dkms-uninstall

(OR) Classic installation (without DKMS):

Build the driver: make

Install the msi-ec kernel module: sudo make install

REBOOT

(Optional) To uninstall: sudo make uninstall

From AUR (Arch Linux)

Install any AUR helper (yay for example)

Run yay -S msi-ec-dkms-git

On NixOS

Add these lines to your configuration

boot.extraModulePackages = [ config.boot.kernelPackages.msi-ec ];

boot.kernelModules = [ "msi-ec" ];
