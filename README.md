The Mothonic T1/USB media converter requires two drivers:

   * lan78xx (USB controller)
   * dp83tc811 (T1 PHY)

These are included in kernel 4.18 and later. If you have an older version it is strongly recommended to upgrade, if you still want to stay you can use this package to build the drivers.

Check kernel version with:

    uname -a

If you need to upgrade see instructions below.

When the drivers are available they will be loaded automatically as soon as the converter is plugged in and the T1 interface is available for use. It is configured in the same way as a normal ethernet interface.


## Ubuntu 18

Drivers are included in linux-modules-extra. If you have upgraded from earlier versions of Ubuntu you may need to install new kernel and modules packages:
    
    sudo apt install linux-image-4.18.0-25-generic linux-modules-extra-4.18.0-25-generic
    
After reboot the T1 interface is available for use.

## Ubuntu 16

Supports kernel 4.16 which contains lan78xx but not dp83tc811. Make sure linux-modules-extra is installed and build dp83tc811 using this package.


## Raspbian Buster

Install prebuilt dp83tc811.ko module from this repository or build using instructions at:

    https://www.raspberrypi.org/documentation/linux/kernel/building.md

### Raspberry 3:

Install rp3_4.9.75/dp83tc811.ko in /lib/modules/4.19.75-v7+/extra/dp83tc811.ko and run `depmod -a`

### Raspberry 4:

Install rp4_4.9.75/dp83tc811.ko in /lib/modules/4.19.75-v7l+/extra/dp83tc811.ko and run `depmod -a`
