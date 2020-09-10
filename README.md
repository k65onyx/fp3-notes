# Fairphone 3 notes

## SoC and main board

The Fairphone uses the [Qualcomm Snapdragon 632 Mobile
Platform](https://www.qualcomm.com/products/snapdragon-632-mobile-platform).
Not much documentation is available to the public, the best available
from the vendor is a [product
brief](https://www.qualcomm.com/media/documents/files/snapdragon-632-mobile-platform-product-brief.pdf).
According to
[Wikipedia](https://en.wikipedia.org/wiki/List_of_Qualcomm_Snapdragon_systems-on-chip#Snapdragon_632,_670_and_675_%282018%29),
these are "pin and software compatible with 625, 626 and 450".  A few
more details can be found about the older [Snapdragon 626](sda626.md).
Wikichip has a [few more
details](https://en.wikichip.org/wiki/qualcomm/snapdragon_600/632)

Alongside a Samsung multi chip package (MCP) lovingly named
[KMRH60014A-B614](https://www.samsung.com/semiconductor/mcp/KMRH60014A-B614/),
providing 4 GiB of LP3DDR volatile memory combined with 64 GiB NAND
with an eMMC 5.1 interface.

![Top portion of the main board PCB of a Fairphone 3](/images/fp3_main_pcb_top.jpg)

## Test Points And Pinout

The following are measures and probes done against an unpowered,
turned off but battery plugged, or a powered device.  Running without
any display or other peripherals.

The labels are arbitrarily assigned, just as a reference.  Measures
and reasoning or net assignment are educated guesses, at the very
best.  Do not rely on any of this data.

**EDIT** : some values has been tested, they will be in **bold**, `~` means reading from AC

![Labeled Test Points Top](/images/test_point_labels.png)

| label | connected to | bat plugged | power on     | comment                                       |
| ----- | ------------ | ----------- | ------------ | --------------------------------------------- |
| A     | BAT 4 / GND  | **0V**      | 0V           | **GND**                                       |
| B     | BAT 4 / GND  | **0V**      | 0V           | **GND**                                       |
| C     |              | **0V**      |              |                                               |
| D     |              | **0V**      |              |                                               |
| E     |              | **0V**      |              |                                               |
| F     | BTN 4        | **1.8V**    | 0V           | power button                                  |
| G     | BAT 1        | **4.18V**   | 4.2V         |                                               |
| H     | BAT 1        | **4.18V**   | 4.2V         |                                               |
| I     |              | **0.2V~**   | 1.32 - 1.36V | (takes a few seconds to rise after power on)  |
| K     |              | **0.1V~**   | 0V           | EDL                                           |
| L     |              | **0V**      | 1.8V         | EDL                                           |
| N     | FP 4         | **0.1V~**   |              |                                               |
| O     | FP 9         | **0.1V~**   |              |                                               |
| P     | FP 3         | **0.1V~**   |              |                                               |
| Q     | FP 2         | **0.1V~**   |              |                                               |
| BTN 1 |              | **0V**      | 0V           | **volume up button**                          |
| BTN 2 |              | **0V**      | 0V           | **volume down button**                        |
| BTN 3 |              | **0V**      | 0V           | **GND**                                       |
| BTN 4 |              | **1.8V**    | 1.8V         | **power button**                              |

Notes on buttons :

* volume up button (on the case) shorts BTN 1 and BTN 3
* volume up button (on the case) shorts BTN 2 and BTN 3
* power button (on the case) shorts BTN 4 and BTN 3

![Labeled Test Points Left Side](/images/test_point_labels2.png)

| label | connected to | bat plugged | power on     | comment                                       |
| ----- | ------------ | ----------- | ------------ | --------------------------------------------- |
| R     |              | **0V**      | 0V           | **GND**                                       |
| S     |              | **0.1V~**   | 0V           | UART RX (?)                                   |
| T     |              | **0.1V~**   | **1.8V**     | **UART TX**                                   |
| W     |              | **0V**      | 0V           | **GND**                                       |


## Similar devices

Other Android devices that use the same Qualcomm platform (non of
which has a LineageOS port so far, it seems):

* Asus Zenfone Max M2 ZB633KL
* Honor 8C
* Zeizu Note 8
* Motorola Moto G7
* Motorola Moto G7 Play
* Motorola Moto G7 Power
* Xiaomi Redmi 7
* Xiaomi Redmi Note 4
* Lenovo K10 Plus

## Links and references

The [iFixIt teardown](https://www.ifixit.com/Teardown/Fairphone+3+Teardown/125573)
provided lots of details about the internals and served as a good
starting point.
