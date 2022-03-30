# Toshiba T3200SX - Info, mods, upgrades, how-tos

_"First, we make the RAM non-standard, then we lock the BIOS to only accept Conner HDDs, then we make the machine painful to open"_  - Toshiba, 1989 (probably)

![image](https://user-images.githubusercontent.com/38451588/155929216-99d89148-76d6-41d2-9388-4ca52fbab9c1.png)


# Interesting features

- Security lug

- Keyboard connector

- 2x ISA slots

- Reset button

- Modem bay


# CPU 

- Intel i386SX @ 16MHz (soldered onto mainboard)

## CPU Upgrade Options

- Cx486SRx² (snaps on top of existing CPU)
- Desolder existing CPU and solder a 486SX on (unknown if this would work - you might also need to replace the oscillator)

https://www.ardent-tool.com/CPU/386_upgrade.html

https://www.amibay.com/forum/amibayers/amioracle/31437-info-on-386-to-486-upgrade-cpus-please?30526-Info-on-386-to-486-Upgrade-cpus-please=

http://ps-2.kev009.com/sandy55/Interposer/386_upgrade.html

# Hard Disk Drive (HDD)

- Interface: Standard IDE

- Conner CP-30104 - this is the 120MB HDD

![image](https://user-images.githubusercontent.com/38451588/156489701-bdf69780-0c87-43c3-b1d6-52d631953f38.png)

- HDD benchmark

![image](https://user-images.githubusercontent.com/38451588/160823671-f259afed-fcee-45d1-baeb-a9dcd5fa5b12.png)


## HDD replacement/upgrades

⚠ Even though the interface is IDE, only certain Conner drives are accepted:

![image](https://user-images.githubusercontent.com/38451588/155963732-d490cf97-a6b0-4f93-8cb7-6e3f3d54fdb1.png)

- An XT-IDE CF adapter is an option

 
 # BIOS
 
 ### How to access the BIOS
 
 - hold ESC while powering on system
 - use TEST3.exe from DOS
 - Press CTRL + SHIFT + F10 when the computer powers on
 - disconnect the clock battery entirely. Wait for a few minutes and power up the computer 

### BIOS Versions

v5.10 | Chip: 003H

### Dumping/Copying/updating BIOS

- Need a TL866 Programmer
- Need replacement 27C1024 chip(s) - 85ns is what appears to be standard for the T3200SXs
- Chips can be OTP (one-time programmable) or UV (requires additional UV lamp)

http://omolini.steptail.com/t3200sx/files/T3200SX_BIOS.PDF

### Modded BIOSes

### CMOS Battery

- ER6 3.6v Lithium battery, plugs into PJ3 (Pin1 +ve, Pin3 -ve). Battery holder fits a AA battery

![image](https://user-images.githubusercontent.com/38451588/160823372-a30813d8-7a9f-48c3-8189-b8cdea874811.png)

- A 330 Ohm resistor has been known to be included in series but I don't know how critical this is
- Can use a 3V normal battery (eg 2032) but a diode may be required to prevent the machine from "charging" the battery
- Battery sits in a holder behind the floppy drive (velcro'd on)
- I've had success replacing this with a 1.5V AA battery.


# RAM/Memory

- 1 MB of RAM is soldered in, expandable up to 13 MB
- 6x 30-pin SIMM slots
- Only 1MB and 2MB modules are supported
- Memory appears to only work in pairs
- ⚠ RAM is restricted to approved modules only and will give an error on boot:

![image](https://user-images.githubusercontent.com/38451588/155928043-60b26f49-17e4-4f8d-aaaf-fcfcfbac2e31.png)

- ⚠ Even though RAM may be tested OK at boot, it may cause random parity errors during use
- With the addition of a Toshiba Expansion Chassis, the T3200SX will accept a standard 16bit memory expansion board and can then be upgraded to 16MB. 

## RAM examples

- 2MB SIMM: HYPERTECB#D 0994 HY444 TPA8309U

- These sticks have been known to work:

![image](https://user-images.githubusercontent.com/38451588/155879068-b4edad2b-308a-4560-9d71-8873c27d0e8f.png)

## RAM hack

https://medium.com/geekculture/the-luggable-laptop-how-does-it-look-today-part-ii-toshiba-t3200-from-1989-6d15ce56eadd
 
# Display Hinges 

- Prone to breakage 😢

![image](https://user-images.githubusercontent.com/38451588/156911198-4833f42c-18ff-4aab-b22c-30f145c78291.png)

Hinge info/pics: https://www.reddit.com/r/retrobattlestations/comments/pd9lpv/toshiba_t3200sx_display_hinges_what_is_the/

# Disassembly

## Screw types 🔩

- Base: 10x 10mm screws (brown)
- Keyboard plate (steel cover): 2x 10mm screws (gold)
- Rear plastic cover (eg with port labels): 2x 8mm screws
- Rear metal cover (I/O port cover): 3x 8mm screws
- Plastic covers on top: 2x 8mm screws (gold)
- Top section screw (anchors the top section, near floppy drive mount): 1x 8mm screw (gold)
- Floppy drive sled: 3x 8mm screws (gold)


http://omolini.steptail.com/t3200sx/mirror/www.ailis.de/~k/archives/21-Toshiba-T3200-SXC.html

## Removing the keyboard/Accessing RAM/BIOS/FPU socket

- Remove 4x screws along the front near the handle (located on bottom)
- Carefully lift up the keyboard along the front, middle edge - it should pop out
- Remove 2x screws from the metal shield
- Unplug keyboard connector from mainboard


## Replacing HDD

_If you're going to go with a crappy HDD, at least let us swap it out easily! Who designed this stupid thing?!_

- ℹRemove RAM modules (well at least the left one)
- Undo the cable clasp (gold screw), you can use a right angle screw driver (I used multi-grips with and a screwdriver bit)
- You should now be able to release the cables and rotate the screen/top section 90 degrees (barely enough to work with)
- Release the power connector from the mainboard - this will give a little more wiggle room (note, the screen connector cannot be unplugged 😠)
- There are 3 screws for the HDD sled, undo #1 and #2 (near the SIMM slot and near the power supply)

![image](https://user-images.githubusercontent.com/38451588/155965401-8e72efff-0b52-400c-99af-8d6a23078a15.png)


- Now you can wiggle the HDD a bit - this will allow you to unplug the IDE cable from the drive (normally blocked by the expansion port connector thingy - again _who_ designed this?)
- Unplug the HDD's power connector, this will reveal the third screw
- Remove last screw and take out the HDD on its sled
- Contemplate the limited upgrade/replacement options 😢

# Maintenance Manual

http://omolini.steptail.com/t3200sx/files/docs/Toshiba%20T3200SX%20-%20Maintenance%20Manual.pdf


# References

https://www.vogons.org/viewtopic.php?t=60109

https://www.vogons.org/viewtopic.php?p=823257#p823257

http://omolini.steptail.com/t3200sx/mirror/www.ailis.de/~k/archives/21-Toshiba-T3200-SXC.html

https://medium.com/geekculture/the-luggable-laptop-how-does-it-look-today-part-ii-toshiba-t3200-from-1989-6d15ce56eadd

https://www.dreamcast.nu/en/how-to-install-ms-dos-on-a-cf-card-without-using-a-floppy/

https://www.reddit.com/r/VintageComputers/comments/rwrgdj/lotech_xt_to_cf_lite_question/

https://www.reddit.com/r/vintagecomputing/comments/s4xgy7/made_a_breakthrough_with_screen_problems_bright/


https://www.youtube.com/watch?v=GzktcqYO8zw


# Unverified/unsorted info

The BIOS only officially supports two drive configurations - "Normal" and "Alternate" both are 40Mb in size. Ways to get full access to the rest of the disk are the same as for any other 286/386:

- download ROM, edit drive table entries in hexideciaml, recalculate checksum, erase/write to a fresh EPROM and install (hardest)
- throw in a network card with the AT version of the XT-IDE ROM in the Boot ROM socket (this gets past any HDD limitations - even LBA, so you could put in almost any IDE drive you want) - this auto detects on startup, and replaces the built in hard drive routines. (solves a lot of issues, but will use up at least your 8 bit ISA slot)
- drive overlay software (like "OnTrack" - usually you want the version from the company that made the hard drive you're installing)

Options 2 and/or 3 I can send up what you need preconfigured.

NB: that XT-IDE ROM will also let you boot from another PC using a serial cable, that could be a godsend if you ever have an issue with the FDD.


CAS line/trace going to pin28 has been intercepted and relayed to pin2.

I have discovered out how to make a standard 2 Meg or 1 Meg 30 pin SIMM work in the T3200sx. What you have to do is cut the trace that is connected to the CASP line (pin 28) and connect that to the CAS line (pin 2). This will result in a 1 Meg module that will work with out the parity error that you will get with out this modification. I have noticed that your 2 Meg Toshiba SIMMs have only 4 chips on them instead of the usual 9 or 3. It would be interesting to try and find the datasheet for the chips and try and figure out the pinout of a 2 Meg Toshiba SIMM. In my T3200sx my 2 Meg modules have 6 chips and I have only been able to find the datasheet for 4 of them. I think that the other 2 are the parity chips but I am not sure. I have found out that pin 19 is grounded on the 2 Meg Toshiba SIMM. I am also guessing that pin 28 on the 2 Meg Toshiba SIMM is A10 but I am not sure. By the way feel free to post this information on your website where ever you think that people will read it. 



 I removed the old defective drive and installed a newer harddisk with a capacity of 2 GB. Enough for this pretty little machine. The BIOS is not able to recognize this harddisk so it is necessary to tell the BIOS that no harddisk is installed. Otherwise it will end up in an error message and it is not able to boot. Yes, if you disable the harddisk in the BIOS you can't boot from it. But no problem. The machine has a floppy drive so I created a boot disk with a linux kernel on it. Linux recognizes the harddisk even if it is not enabled in the BIOS so the kernel can mount the harddisk as the Root-Partition.
