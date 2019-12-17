# RISC-V dev board on GD32V platform

## Development instructions

* Install VS Code
* Install PlatformIO plugin
* Get `GD32V` platform definition: `platformio platform install gd32v`

Pin map can be found [here](https://longan.sipeed.com/en/)

## To setup DFU for Linux:

Add to `udev` file : /etc/udev/rules.d/99-platformio-udev.rules

```
# Longan Nano
ATTRS{idVendor}=="28e9", ATTRS{idProduct}=="0189", MODE="0666"
```

Reboot

Now you should be able to upload firmware through `dfu-util` fork found [here](https://www.susa.net/wordpress/2019/10/longan-nano-gd32vf103/)

## To upload firmware on Windows:

* Install driver `GD32 MCU Dfu Drivers_v1.0.1.2316`
* The only way to upload firmware is through a forked `dfu-util` that can be found in `GD32 MCU Dfu Tool_v3.8.1.5784`
    * Select DFU device
    * Select firmware from `.pio` folder
    * Tick `verify after download`
    * Click `OK`

## Tutorials

* Good one is [here](https://www.susa.net/wordpress/2019/10/longan-nano-gd32vf103/)
* Misc files can be found [here](http://dl.sipeed.com/LONGAN/Nano/Tools)
