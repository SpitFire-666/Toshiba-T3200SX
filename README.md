# ToshibaT3200SX

# Interesting features

### Security lug

### Keyboard connector

### 2x ISA slots


# Hard Disk Drive (HDD)

- Interface: Standard IDE

Conner CP-30104

![image](https://user-images.githubusercontent.com/38451588/155868502-bcbbdce4-fc74-4277-a7fe-7b589f1a988b.png)


 I removed the old defective drive and installed a newer harddisk with a capacity of 2 GB. Enough for this pretty little machine. The BIOS is not able to recognize this harddisk so it is necessary to tell the BIOS that no harddisk is installed. Otherwise it will end up in an error message and it is not able to boot. Yes, if you disable the harddisk in the BIOS you can't boot from it. But no problem. The machine has a floppy drive so I created a boot disk with a linux kernel on it. Linux recognizes the harddisk even if it is not enabled in the BIOS so the kernel can mount the harddisk as the Root-Partition. 
 
 # BIOS
 
 ### Accessing the BIOS
 
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




# RAM

- Standard 1 MB of RAM, expandable up to 13 MB
- 6x 30-pin SIMM slots
- ⚠ RAM is restricted to approved modules only
- ⚠ Even though RAM may be tested OK at boot, it may cause random parity errors during use

2MB SIMM: HYPERTECB#D 0994 HY444 TPA8309U


These sticks have been known to work:

![image](https://user-images.githubusercontent.com/38451588/155879068-b4edad2b-308a-4560-9d71-8873c27d0e8f.png)

## RAM hack

CAS line/trace going to pin28 has been intercepted and relayed to pin2.

I have discovered out how to make a standard 2 Meg or 1 Meg 30 pin SIMM work in the T3200sx. What you have to do is cut the trace that is connected to the CASP line (pin 28) and connect that to the CAS line (pin 2). This will result in a 1 Meg module that will work with out the parity error that you will get with out this modification. I have noticed that your 2 Meg Toshiba SIMMs have only 4 chips on them instead of the usual 9 or 3. It would be interesting to try and find the datasheet for the chips and try and figure out the pinout of a 2 Meg Toshiba SIMM. In my T3200sx my 2 Meg modules have 6 chips and I have only been able to find the datasheet for 4 of them. I think that the other 2 are the parity chips but I am not sure. I have found out that pin 19 is grounded on the 2 Meg Toshiba SIMM. I am also guessing that pin 28 on the 2 Meg Toshiba SIMM is A10 but I am not sure. By the way feel free to post this information on your website where ever you think that people will read it. 

 You need 30 pin SIMM modules with a capacity of 1 MB or 2 MB. 4 MB modules are not recognized. 
 
 I have 2 x 2MB ram cards for Toshiba T3200. They are each Kingston KTT-3200SXC/4, seem to work ok

# Disassembly

http://omolini.steptail.com/t3200sx/mirror/www.ailis.de/~k/archives/21-Toshiba-T3200-SXC.html

## Removing the keyboard

- Remove 4x screws along the front near the handle (located on bottom)
- Carefully lift up the keyboard along the front, middle edge - it should pop out


# References

https://www.vogons.org/viewtopic.php?t=60109

https://www.vogons.org/viewtopic.php?p=823257#p823257

http://omolini.steptail.com/t3200sx/mirror/www.ailis.de/~k/archives/21-Toshiba-T3200-SXC.html

https://medium.com/geekculture/the-luggable-laptop-how-does-it-look-today-part-ii-toshiba-t3200-from-1989-6d15ce56eadd
