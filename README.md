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

![Labeled Test Points](/images/test_point_labels.png)

| label |  connected to 	| bat plugged 	| power on     	|  comment                                     	|
| ----- | ---------------	| ------------	| -------------	| ---------------------------------------------	|
| A   	|     BAT 4     	|      0V     	|      0V      	| GND                                          	|
| B   	|     BAT 4     	|      0V     	|      0V      	| GND                                          	|
| C   	|               	|             	|              	|                                              	|
| D  	|               	|             	|              	|                                              	|
| E  	|               	|             	|              	|                                              	|
| F   	|     BTN 4     	|             	|              	| power button                                 	|
| G  	|     BAT 1     	|     4.2V    	|              	|                                              	|
| H  	|     BAT 1     	|     4.2V    	|              	|                                              	|
| I   	|               	|      0V     	| 1.32 - 1.36V 	| (takes a few seconds to rise after power on) 	|
| K   	|               	|      0V     	|      0V      	|                                              	|
| L   	|               	|      0V     	|     1.78V    	|                                              	|
| N  	|               	|             	|              	|                                              	|
| O   	|               	|             	|              	|                                              	|
| P   	|               	|             	|              	|                                              	|
| Q   	|               	|             	|              	|                                              	|
| R   	|               	|      0V     	|              	|                                              	|
| S   	|               	|      0V     	|      0V      	|                                              	|
| T   	|               	|      0V     	|     1.78V    	|                                              	|

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

The [iFixIt
teardown](https://www.ifixit.com/Teardown/Fairphone+3+Teardown/125573)
provided lots of details about the internals and served as a good
starting point.
