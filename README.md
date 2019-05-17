# How to build alone

## setup environment

    source environment-setup    //<ANDROID_SOURCE> directory

you also can setup manually:

    cd <ANDROID_SOURCE>
    export PATH=$PATH:`pwd`/prebuilts/gcc/linux-x86/arm/arm-eabi-4.6/bin:`pwd`/bootable/bootloader/uboot-imx/tools
    export ARCH=arm
    export CROSS_COMPILE=arm-eabi-

## build kernel default case

    cp arch/arm/configs/imx_v7_android_no_logo_defconfig arch/arm/configs/imx_v7_android_defconfig
    make imx_v7_android_defconfig

## build kernel with keep uboot logo feature

    cp arch/arm/configs/imx_v7_android_logo_defconfig arch/arm/configs/imx_v7_android_defconfig
    make imx_v7_android_defconfig

## build

    make uImage LOADADDR=0x10008000
