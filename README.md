# Ikoka Meshtastic Device

A Meshtastic device based on the [Seeed Studio XIAO nRF52840](https://www.seeedstudio.com/Seeed-XIAO-BLE-nRF52840-p-5201.html) and EBYTE E22-XXXMXXS series LoRa modules. Pinout matches the [Meshtastic xiao_ble variant](https://github.com/meshtastic/firmware/tree/master/variants/xiao_ble).

The focus is on small size without an onboard display or buttons, meaning it must be used with [Meshtastic client software](https://meshtastic.org/docs/software/), or as a remote repeater managed with [remote node administration](https://meshtastic.org/docs/configuration/remote-admin/).

## Connectors

* JST PH (2mm pitch) connector for 1S LiPo
* JST PH (2mm pitch) connector for solar panel ([TI BQ25100](https://www.ti.com/product/BQ25100) charge IC on XIAO nRF52840, max 6.45V), connected to USB 5V
* Qwiic connector for I²C sensors

## Libraries Used

* [SnapMagic E22-900M30S footprint & symbol](https://www.snapeda.com/parts/E22-900M30S/EBYTE/view-part/)
* [Seeed Studio XIAO nRF52840 Eagle footprint](https://files.seeedstudio.com/wiki/XIAO-BLE/Seeed-Studio-XIAO-nRF52840-footprint-eagle.lbr) (modified with battery pads copied from XIAO ESP32C3 footprint)

## PCB Images

![PCB Top](ikoka-nano-pcb-top.png?raw=true)
![PCB Bottom](ikoka-nano-pcb-bottom.png?raw=true)
