# Ikoka Nano Meshtastic Device

A Meshtastic device based on the [Seeed Studio XIAO nRF52840](https://www.seeedstudio.com/Seeed-XIAO-BLE-nRF52840-p-5201.html) and EBYTE E22-XXXMXXS series LoRa modules. Pinout matches the [Meshtastic xiao_ble variant](https://github.com/meshtastic/firmware/tree/master/variants/xiao_ble).

The focus is on small size without an onboard display or buttons, meaning it must be used with [Meshtastic client software](https://meshtastic.org/docs/software/), or as a remote repeater managed with [remote node administration](https://meshtastic.org/docs/configuration/remote-admin/).

## Connectors

* JST PH (2mm pitch) connector for 1S LiPo
* JST PH (2mm pitch) connector for solar panel ([TI BQ25100](https://www.ti.com/product/BQ25100) charge IC on XIAO nRF52840, max 6.45V), connected to USB 5V
* Qwiic connector for I²C sensors

## Libraries Used

* [SnapMagic E22-900M30S footprint & symbol](https://www.snapeda.com/parts/E22-900M30S/EBYTE/view-part/)
* [Seeed Studio XIAO nRF52840 Eagle footprint](https://files.seeedstudio.com/wiki/XIAO-BLE/Seeed-Studio-XIAO-nRF52840-footprint-eagle.lbr) (modified with battery pads copied from XIAO ESP32C3 footprint)

## Building One

### Ordering PCBs

* Use the `ikoka-nano.cam` in EAGLE's CAM processor to generate Gerbers in a ZIP file
* Upload this ZIP file to [JLCPCB](https://jlcpcb.com/) to order the PCBs; the default JLCPCB settings work fine

### Ordering Components

* LCSC
  * 1* [EBYTE E22-900M30S](https://www.lcsc.com/product-detail/LoRa-Modules_Chengdu-Ebyte-Elec-Tech-E22-900M30S_C411294.html)
  * 1* [JST SM04B-SRSS-TB(LF)(SN)](https://www.lcsc.com/product-detail/Wire-To-Board-Wire-To-Wire-Connector_JST-SM04B-SRSS-TB-LF-SN_C160404.html)
  * 2* [JST S2B-PH-SM4-TB(LF)(SN)](https://www.lcsc.com/product-detail/Wire-To-Board-Wire-To-Wire-Connector_JST-S2B-PH-SM4-TB-LF-SN_C295747.html)
  * 1x [Murata GRM31CR60J107ME39L](https://www.lcsc.com/product-detail/Multilayer-Ceramic-Capacitors-MLCC-SMD-SMT_Murata-Electronics-GRM31CR60J107ME39L_C77085.html)
* Seeed Studio
  * 1* [Seeed Studio XIAO nRF52840](https://www.seeedstudio.com/Seeed-XIAO-BLE-nRF52840-p-5201.html)

### Assembling the PCB

(TODO)

### Flashing

Follow the instructions at [meshtastic/firmware/variants/xiao_ble/](https://github.com/meshtastic/firmware/tree/master/variants/xiao_ble).

## PCB Images

![PCB Top](ikoka-nano-pcb-top.png?raw=true)
![PCB Bottom](ikoka-nano-pcb-bottom.png?raw=true)
