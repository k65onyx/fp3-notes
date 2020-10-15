# Receiving boot info from UART

The access to the TX pin on the fairphone and boot the device can be achieve without any soldering thanks to the possibility to disassemble the phone.

After taking appart the motherboard (following fairhpone's official video or ifixit guide), the only module that you may want to plug is the bottom module (having microphone but also the vibration motor).

I haven't tested to boot without the bottom module yet.

## Minimal boot procedure

![Annotated photo of the disassembled phone](/images/fp3_minimal_boot_annotated.jpg)

On the photo we can see that the only parts needed are:

* motherboard
* bottom module (vibration is helpfull to know the phone is powering on)
* battery
* a piece of metal (here a male end of a jumper cable)

The different annotated points are :

* 1 : volume up
* 2 : volume down
* 3 : GND (ground)
* 4 : power button
* 5 : TX (tranfert pin of the UART)

The 3 buttons on the side of the phone : volume up, volume down, power, all shorts the respective points 1, 2 and 4 to the ground at 3.

So you can reproduce a power button press by shorting point 3 and 4 together, volume up with 3 and 1, volume down with 3 and 2.

To get UART connection using a USB device we need to at least GND and TX, I have read that VCC can be needed but it is unclear on the situation that requires it and it may be a power problem (how the UART adapter draws power either from the USB or the connected device).

Connect to the phone's GND is the easiest as many points are in fact GND (see README.md), also all the big metalic shells are grounded, the back-plate/metallic shield on the other side is also grounded.

Before connecting the UART pins you should put the battery in place, it will add weight to the whole making manipulation easier and if you are not soldering anything to TX you will need to keep one hand on it.

Now is the time to also prepare the command to start the UART communication on your computer. On linux I would recommend something like :

```
sudo screen -L /dev/ttyUSB0 115200
```

The `-L` option will output a log (`screenlog.0`) of everything and the baud rate of the FP3 is 115200. Your USB device might appear on an other ttyUSB number. `sudo` is needed if you are not already logged as `root`.

Using simple jumper cable I found the easiest way is to just put the GND end under the motherboard so it stays in place dur to the weight of the system and touches the grounded back-plate.

The smaller point 5 is harder to get so either soldering a cable would help, otherwise you will need to use your off hand to keep your RX pin (from the USB adapter) touching this TX.

While keeping TX pin in contact you can start the command you prepared on your computer first then power on the phone by shortening points 3 and 4.

No maintaining contact will usually output garbage but as soon as the contact is OK again the following will be clean (there is no disconnection mecanism here).
