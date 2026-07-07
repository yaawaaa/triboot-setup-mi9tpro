# Installing Linux on your device

### Prerequisites
- [Ubuntu Image](https://sourceforge.net/projects/linux-raphael/files/)
  
### Flashing the Ubuntu Rootfs
> [!NOTE]
> Make sure your device is in TWRP mode for this step.

1. Move your chosen Ubuntu rootfs image file (like the Phosh 7.1 build) onto your phone's storage or a USB OTG drive. 
2. You can perform this step using the TWRP terminal directly on the phone, or by using an ADB terminal on your PC.

Execute the following command to flash the image file to the dedicated Linux partition:
```cmd
dd if=/path/to/your/rootfs.img of=/dev/block/by-name/ubuntu bs=4096
```

#### Flashing your rooted boot image
> Replace `path\to\magisk_patched.img` with the actual path of the image
```cmd
fastboot flash boot path\to\magisk_patched.img
```

### Reboot to Android
```cmd
fastboot reboot
```

#### Finishing setup
- Open the **Magisk** app again.
- Follow the instructions on the screen, and your device should reboot after a few seconds.

### Copying the rooted boot image
> After your device has booted back into Android
```cmd
adb shell "su -c cp /dev/block/by-name/boot /sdcard/rooted_boot.img" & adb pull /sdcard/rooted_boot.img
```
- A superuser request for Shell might appear on your phone's screen. If it does, grant it access.
- If the command fails, open **Magisk**, click on `Superuser`, find **Shell**, and grant it access.

## [Next step: Installing Windows](3-install.md)













































