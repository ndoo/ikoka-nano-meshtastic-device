# Ikoka Nano Meshtastic Device

A Meshtastic device based on the [Seeed Studio XIAO nRF52840](https://www.seeedstudio.com/Seeed-XIAO-BLE-nRF52840-p-5201.html) and EBYTE E22-XXXMXXS series LoRa modules. Pinout matches the [Meshtastic xiao_ble variant](https://github.com/meshtastic/firmware/tree/master/variants/xiao_ble).

The focus is on small size without an onboard display or buttons, meaning it must be used with [Meshtastic client software](https://meshtastic.org/docs/software/), or as a remote repeater managed with [remote node administration](https://meshtastic.org/docs/configuration/remote-admin/).

## Connectors

* USB-C for power and data
* Qwiic connector for I²C sensors

## Future Plans

* Add a boost converter and restore battery-powered operation

## Libraries Used

* [SnapMagic E22-900M30S footprint & symbol](https://www.snapeda.com/parts/E22-900M30S/EBYTE/view-part/)
* [SparkFun KiCad Libraries](https://github.com/sparkfun/SparkFun-KiCad-Libraries)
* [SeeedStudio OPL KiCad Library](https://github.com/ndoo/OPL_Kicad_Library/tree/xiao-ble-symbols) (forked to add missing XIAO nRF5240 symbol)

## Building One

### Software Required

* The files were created in [KiCad](https://www.kicad.org/) 8
* Clone this git repository recursively, i.e. with `--recursive`

### Ordering PCBs

* Follow the instructions to generate Gerbers at your PCB house, e.g. [JLCPCB PCB Files Preparation](https://jlcpcb.com/help/catalog/180-PCB-Files-Preparation)
* Default 1.6mm 2-layer PCB settings should work well, this PCB passes DRC based on JLCPCB specifications (other than the silkscreen of XIAO module being clipped by the PCB edge)
  * PCBA: I used [[https://github.com/bennymeg/Fabrication-Toolkit|JLC PCB Plug-in for KiCad]] to generate a BOM and CPL file compatible with JLCPCB PCBA

### Ordering Components

* LCSC
  * 1* [EBYTE E22-900M30S](https://www.lcsc.com/product-detail/LoRa-Modules_Chengdu-Ebyte-Elec-Tech-E22-900M30S_C411294.html)
  * 1* [JST SM04B-SRSS-TB(LF)(SN)](https://www.lcsc.com/product-detail/Wire-To-Board-Wire-To-Wire-Connector_JST-SM04B-SRSS-TB-LF-SN_C160404.html)
  * 1* [Murata GRM31CR60J107ME39L](https://www.lcsc.com/product-detail/Multilayer-Ceramic-Capacitors-MLCC-SMD-SMT_Murata-Electronics-GRM31CR60J107ME39L_C77085.html)
* Seeed Studio
  * 1* [Seeed Studio XIAO nRF52840](https://www.seeedstudio.com/Seeed-XIAO-BLE-nRF52840-p-5201.html)

### Assembling the PCB

1. Solder U2 E22 module
2. Solder C1
3. Solder U1 XIAO nRF52840
4. Solder Qwiic socket

### Flashing

Follow the instructions at [meshtastic/firmware/variants/xiao_ble/](https://github.com/meshtastic/firmware/tree/master/variants/xiao_ble).

### Enclosure

A snap-fit 3D printable enclosure is available in the `enclosures` folder.

![ikoka nano in enclosure](assets/ikoka-nano-meshtastic-device.png)

## PCB Images

![rotating](https://ndoo.github.io/ikoka-nano-meshtastic-device/rotating.gif)

![top](https://ndoo.github.io/ikoka-nano-meshtastic-device/top.png)
![bottom](https://ndoo.github.io/ikoka-nano-meshtastic-device/bottom.png)
