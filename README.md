# Lenovo V15 G4 AMN Linux Touchpad Patch

This repository contains kernel patches for different versions of the Linux kernel to enable the touchpad on the Lenovo V15 G4 AMN notebook to work seamlessly with Linux. The Lenovo V15 G4 AMN notebook is known to have some compatibility issues with the Linux kernel, and this project aims to resolve those issues by providing the necessary kernel patches.

## Compatibility

These patches have been tested and are compatible with the following Linux kernel versions:

- Linux Kernel 5.4
- Linux Kernel 5.10
- Linux Kernel 5.15
- Linux Kernel 6.1
- Linux Kernel 6.2
- Linux Kernel 6.3
- Linux Kernel 6.4

## Usage

To make the touchpad of your Lenovo V15 G4 AMN notebook work on Linux, follow these steps:

1. Install the DSDT Patches from https://github.com/hacklian/lenovo_82yu_dsdt_patches

2. Clone this repository to your local machine:
```bash
git clone git@github.com:hacklian/lenovo_82yu_i2c_hid-dkms.git
```

3. Change into the project directory:
```bash
cd lenovo_82yu_i2c_hid-dkms
```

4. Run the build.sh script to build the kernel module for your specific kernel version:
```bash
./build.sh --kernel-version 6.5
```
If you omit the kernel version, the build script will create a version for the currently running kernel.


5. After the build process is complete, you can install the built module using dkms. Run the following command to install the module:
```bash
sudo dkms install ./dist/{KERNEL_VERSION}
```

6. Run DKMS Autoinstall and recreate the ramdisk
```bash
sudo dkms autoinstall
sudo mkinitcpio -P
```

7. Reboot your system to apply the changes:
```bash
sudo reboot now
```

The touchpad on your Lenovo V15 G4 AMN notebook should now work properly with Linux.

## Contributing
If you encounter issues or have improvements to the patches, feel free to open an issue or submit a pull request. Your contributions are welcome and appreciated.

## License
This project is licensed under the GNU GENERAL PUBLIC License. See the LICENSE file for details.

The Linux Kernel is provided under the SPDX-License-Identifier: GPL-2.0 WITH Linux-syscall-note. See the COPYING file for details.