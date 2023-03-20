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

## Math Co-Processor

- Intel 80387SX

## CPU Upgrade Options

- Cx486SRx² (snaps on top of existing CPU)
- Desolder existing CPU and solder a 486SX on (unknown if this would work - you might also need to replace the oscillator)

https://www.ardent-tool.com/CPU/386_upgrade.html

https://www.amibay.com/forum/amibayers/amioracle/31437-info-on-386-to-486-upgrade-cpus-please?30526-Info-on-386-to-486-Upgrade-cpus-please=

http://ps-2.kev009.com/sandy55/Interposer/386_upgrade.html

# Hard Disk Drive (HDD)

### Interface

Standard IDE. Note that the mainboard uses a larger 44-pin connector (PJ12) but with the last 4 pins unpopulated:

![image](https://user-images.githubusercontent.com/38451588/224856602-b8fe5677-807f-4e51-b0ae-c71451bf6a8f.png)


![image](https://user-images.githubusercontent.com/38451588/224856507-c3ae42d6-c6eb-4255-8efa-dcf3c1d28b2f.png)

### HDD types

#### Conner CP-30104 (120MB)

![image](https://user-images.githubusercontent.com/38451588/156489701-bdf69780-0c87-43c3-b1d6-52d631953f38.png)

HDD benchmark: using CheckIt 2.1

- Average seek time: 18.9ms
- Track to Track seek time: 6.5ms
- Transfer Speed: 339.6K/Second


#### Conner CP-3044 (40MB)

![image](https://user-images.githubusercontent.com/38451588/224888070-3081cfb4-808c-4d20-a789-e7bc255df2d1.png)


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



## 🔩 Screw types

### Screen

- Screen base/hinge (underneath power/status LED cover): 2x 8mm screws
- Screen top (under the rubber pads): 2x 8mm
- Grounding wire: 1x 8mm
- Plasma frame: 4x 8mm

Contrast board: FH4V02 (T5200 is FH3V04)

Plasma display is the same as the T5200, however T3200SX frame is metal and T5200 frame is plastic

- Base: 10x 10mm screws (brown)
- Rear expansion plate/metal cover: 3x 8mm
- Keyboard plate (steel cover): 2x 10mm screws (gold)
- Rear plastic cover (eg with port labels): 2x 8mm screws
- Rear metal cover (I/O port cover): 3x 8mm screws
- Plastic covers on top: 2x 8mm screws (gold)
- Top section screw (anchors the top section, near floppy drive mount): 1x 8mm screw (gold)
- Floppy drive sled: 3x 8mm screws (gold)
- Modem access panel: 3x ??mm screws


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

![image](https://user-images.githubusercontent.com/38451588/224858011-e080e083-5c6f-4400-be13-bc9f84d1aa2f.png)


- Now you can wiggle the HDD a bit - this will allow you to unplug the IDE cable from the drive (normally blocked by the expansion port connector thingy - again _who_ designed this?)
- Unplug the HDD's power connector, this will reveal the third screw
- Remove last screw and take out the HDD on its sled
- Contemplate the limited upgrade/replacement options 😢

# Maintenance Manual

http://omolini.steptail.com/t3200sx/files/docs/Toshiba%20T3200SX%20-%20Maintenance%20Manual.pdf


# Plasma display

- Display will function OK without contrast control board plugged in/present
- Display will NOT power up without both the power (J2) and signal (J1) plugs plugged in
- Display is interchangeable with T5200
- PCB: m480t640hb02b
- PDP: MD480T640PG3

# References


| Desc | Link |
|-|-|
| | https://www.vogons.org/viewtopic.php?t=60109 |
| T3200SX Specs | https://www.manualslib.com/manual/330225/Toshiba-T-Series-T3200sx.html |
| | https://www.vogons.org/viewtopic.php?p=823257#p823257 |
| | http://omolini.steptail.com/t3200sx/mirror/www.ailis.de/~k/archives/21-Toshiba-T3200-SXC.html |
| | https://medium.com/geekculture/the-luggable-laptop-how-does-it-look-today-part-ii-toshiba-t3200-from-1989-6d15ce56eadd |
| | https://www.dreamcast.nu/en/how-to-install-ms-dos-on-a-cf-card-without-using-a-floppy/ |
| | https://www.reddit.com/r/VintageComputers/comments/rwrgdj/lotech_xt_to_cf_lite_question/ | 
| | https://www.reddit.com/r/vintagecomputing/comments/s4xgy7/made_a_breakthrough_with_screen_problems_bright/ |
| | https://www.youtube.com/watch?v=GzktcqYO8zw


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


You need a second HN27C1024-85 chip and a EPROM flash tool like the MiniPro. Might also need a UV bulb to erase the chip, though a week or so in direct sunlight should also work to erase it.

It recognises the drive as 40MB but you can use software that is resident in the MBR to expand it to 500-ish MB. Check out his page for more info: http://www.steptail.com/toshiba_t-series_support:toshiba_t3200sx


 I strongly recommend using a stock replacement - 3.6V Lithium same size/shape as a normal AA with tag leads.
This is because the layout of the T3200 makes it damn near impossible to fit a dual AA holder properly, mine is now firmly squished against the IDE and FDD cables :/ its firm and the machine didn't mind, but it's not as tidy as the T5200 where the AA holder fits perfectly in the original position.

I found out what it does like though, one pair DID work, they're 9 chip 120ns and either 2Mb or 4Mb in capacity - the extended memory test stopped at ~2400KB with a read/write error (not a parity error). None of the others worked, so I need to work out if they're the magic 2Mb SIMMs and that's why it worked, or if they're general 4Mb parity SIMMs - in which case I'll have to hop on ebay. 


the details given for the memory upgrade kits indicate that this system will probably only take 1MB SIMMs (2MB kit), with the 4MB kit being a designer dream for the marketing people to convince prospective buyers with how 'future-proof' you would be to buy one of these systems. Check out the brochure. Only suit wearing yuppies are the target market, not computer savvy nerds like us. (8MB+ download)


The SIMMs that it responded to are Mitsubishi 120ns 256KB but it appears it's hardcoded for 1024KB modules - it must have pretended they were 1024KB (if I add up the failure point + 640KB conventional I get a perfect 3MB). SIMM model number was Mitsubishi MH25609BJ-12 (and I checked the chips are in fact 256-12 models). It must have overwritten the SIMM modules 4 times in the test, and I wonder if those Mitsubishi chips are wired to allow this and that's why they worked? (I need to study more on this topic I think :) ).

