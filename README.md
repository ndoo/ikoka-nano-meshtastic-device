# Ikoka Nano Meshtastic Device

A Meshtastic device based on the [Seeed Studio XIAO nRF52840](https://www.seeedstudio.com/Seeed-XIAO-BLE-nRF52840-p-5201.html) and EBYTE E22-XXXMXXS series LoRa modules. Pinout matches the [Meshtastic xiao_ble variant](https://github.com/meshtastic/firmware/tree/master/variants/xiao_ble).

The focus is on small size without an onboard display or buttons, meaning it must be used with [Meshtastic client software](https://meshtastic.org/docs/software/), or as a remote repeater managed with [remote node administration](https://meshtastic.org/docs/configuration/remote-admin/).

## Connectors

* USB-C for power and data
* Qwiic connector for I²C sensors
* Battery connectors (PicoBlade 1.25-2P)
* Solar connector (PicoBlade 1.25-2P, 4.45 to 6.45 V - BQ25100 charge IC)

## Libraries Used

* [SnapMagic E22-900M30S footprint & symbol](https://www.snapeda.com/parts/E22-900M30S/EBYTE/view-part/)
* [SparkFun KiCad Libraries](https://github.com/sparkfun/SparkFun-KiCad-Libraries)
* [SeeedStudio OPL KiCad Library](https://github.com/ndoo/OPL_Kicad_Library/tree/xiao-ble-symbols) (forked to add missing XIAO nRF5240 symbol)

## Building One

### Software Required

* The files were created in [KiCad](https://www.kicad.org/) 8
* Clone this git repository recursively, i.e. with `--recursive`

### Ordering PCBs

* Generate the production files
  * Install [kicad-jlcpcb-tools](https://github.com/Bouni/kicad-jlcpcb-tools)
  * Open the PCB file
  * Tools -> External Plugins -> JLCPCB Tools
  * Look over the Bill of Materials list and perform any substitutions required
  * Click Generate
* Order the PCBs
  * Use the Gerbers, BOM and CPL files in `jlcpcb/production_files`
  * Default 1.6mm 2-layer PCB settings should work well, this PCB passes DRC based on JLCPCB specifications (other than the silkscreen of XIAO module being clipped by the PCB edge)

### Ordering Components

* Check the exported BOM file in `jlcpcb/production_files`

### Assembling the PCB

I suggest PCBA, but I used handsoldering pads and all SMDs are 0603 or larger so can be hand-soldered.

1. Solder the SMD components
  1. D1, C4, D2, R1
  2. U3, Q1
  3. R2, C3
  4. C1, C2
  5. L1
2. Solder the connectors
  1. Qwiic connector
  2. Solar connector, battery connector x2
3. Solder the XIAO BLE (solder 1-2 pins first then verify the rear VBAT hole is lined up well, before soldering the rest of the pads)
4. Solder the E22-900M30S module

### Flashing

Follow the instructions at [meshtastic/firmware/variants/xiao_ble/](https://github.com/meshtastic/firmware/tree/master/variants/xiao_ble).

### Enclosure

A snap-fit 3D printable enclosure is available in the `enclosures` folder. **This has not been updated for the latest board design ([2b17a53](https://github.com/ndoo/ikoka-nano-meshtastic-device/commit/2b17a53b4cfc0f9a9a845ffaf8d8353723f1d552)).**

## PCB Images

![rotating](https://ndoo.github.io/ikoka-nano-meshtastic-device/rotating.gif)

![top](https://ndoo.github.io/ikoka-nano-meshtastic-device/top.png)
![bottom](https://ndoo.github.io/ikoka-nano-meshtastic-device/bottom.png)
