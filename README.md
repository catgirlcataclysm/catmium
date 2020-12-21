# Cadmium, Linux for MT8183-based Lenovo Chromebook Duet

## Installation
- ``` ./build-all <pendrive> ``` On a Linux machine(ChromeOS doesn't count(except in linux chroot)). For Debian rootfs, binfmt(if host isn't aarch64) and debootstrap need to work correctly.
- Enable developer mode
- Plug <pendrive> into duet via usb-c to usb-a adapter
- Boot from USB
- After running ``` ./install-to-emmc ``` after connecting to internet, Debian _should_ be installed on internal emmc memory
- To update kernel on eMMC memory run: ```./install-kernel``` from <pendrive>

### OR
- Enable developer mode
- Write uncompressed release image to pendrive
- Boot from USB
- Run ```./install-to-emmc```

#### Due to GPU working correctly only in 21.0.0 mesa, only llvmpipe driver is available until there is a release with support for Mali G72 in Panfrost
#### *Binary drivers are unsupported in Cadmium and never will be*

## Dependencies on build machine
- Recent Linux distribution
- Binfmt when Debian rootfs is used
- ```debootstrap``` when Debian rootfs is used
- ```qemu-user-static vboot_utils u-boot-tools```
- Build dependencies for kernel compilation
