# Support

* If you like my work, you can support me through https://ko-fi.com/DualTachyon

# Persona non-grata

Don't be a dick or entitled, or you may find yourself blocked from using future firmware.

- **"fe8769"** : "I'm smarter than you and won't try your suggestion" and blackmailing with fake threats of calling law enforcement.
- **"Nobody@TG"** : Insulting everyone's intelligence by saying a solution doesn't work and blaming it on the English language.
- **John Telek** : Facebook keyboard warrior that prefers to complain about firmware instead of reporting bugs so they can get fixed.

# Forewarning

- **This firmware is not for newbies to radios or DMR. Go visit somewhere else if you are a newbie.**
  - **Newbies are not welcome, you're a giant burden of support on everyone and a general stain. Go play with Walmart radios instead.**.
- **If you don't know what this firmware is about, just use Radtel firmware.**
- **If you need a ready made codeplug to get started, just use Radtel firmware.**
- **If you need to tell everyone on github that you have 40 years of computer and radio experience, just use Radtel firmware.**
- **If you double click a file and nothing happens, just use Radtel firmware.**
- **If you can't find a download for flashers, just use Radtel firmware.**
- **If you live on Facebook complaining all day, without writing detailed bug reports, go somewhere else**
- **If you think I'm annoying, then don't use my firmware! I never forced you to use my stuff. Go and use the official firmware.**

If you fit in any of the above, stick to Official Radtel firmware as this firmware is not for you.

# CPS warning

Official 3.18 broke CPS compatibility entirely and in very counter productive ways. 3.18 CPS and beyond will not be supported and from Beta 41 onwards, only [Joel's RT-4D CPS](https://github.com/jcalado/rt4d-cps) will be supported. I have better things to do than change the entire firmware to accomodate random and big CPS changes, most of which didn't need to happen.

# SPI Flash

**Always back up your SPI flash before installing any beta! No support will be given to those losing the calibration settings who didn't make a backup**

# Changelog

You can find more friendly documentation at [wiki](https://github.com/jcalado/rt-4d-fw-beta/wiki) by [Joel](https://github.com/jcalado). Be aware that the documentation can sometimes lag behind the releases but will eventually get updated.

I have better things to do than wait for a fixed DMR firmware that has been available for weeks but still not published, so here's the release. DMR firmwares v1.2.0.28 (20260113) and v1.2.0.31 (20060123) are good. Don't ask where to get it, I don't know where. Don't harass other people to give it to you.

- Beta 41
  - DMR Firmware 1.2.0.28 appears to fix the freeze/hang issues with RX and the RF chip. This is now the minimum version required.
  - Inherited the following from Official v3.19-v3.22 firmware:
    - New DMR, Dual Standby and Save Mode logics. Combined with 1.2.0.28, this improves Analogue <> DMR transitions.
    - Simultaneous Analogue and DMR settings, but the menus remain in the style of 3.16 and earlier.
    - RX/TX limits (RX+TX, RX only, TX only).
    - TX/RX denoise for DMR.
    - Support for the new UTF16 table for sending SMS.
    - Reduced storage space for each RX groups, and increased the maximum number of groups to 150.
      - This is different than what newer Radtel firmware does, and I will not break the entire CPS just to support this.
    - Removed holding 0 while powering on.
    - Removed holding * while powering on.
    - Removed color code scan.
    - Removed the State Timer and State screen.
    - Moved "Offset Dir" to "Offset Frequency". Use the green button to toggle +/-.
    - Converged the 2 version options to "Radio Info" along with some calibration data.
  - Air Copy has been removed (holding Green/Red buttons on power up).
  - Apart from Channels and RX Groups, other CPS layout changes from Official v3.18+ were not inherited.
  - DMR can now be tuned between 70.000-79.999MHz.
  - Added "Set RX Freq" to "Channel Setup". You can now edit RX frequencies when in Channel/Zone mode.
  - Added holding * while powering on to always enter PC programming mode.
  - Implemented settings corruption prevention different than Official v3.18+, which could make the 4D boot with only the lights on.
  - If Settings and Calibration ever get corrupted, the RT-4D will display such information and enter automatic programming mode.
  - All RX groups are now always present, but can be empty / unused.
    - This fixes bugs with Official firmware where deleting one group affected channels using groups after the deleted one.
    - Pressing PTT when promiscuous is disabled, from a channel using an empty RX group will display an error.
  - Pressing PTT when the current ID is 0 will display an error. This also applies to self ID (main Radio ID or per-channel ID).
  - Voice playback support has been removed entirely.
  - Renamed the display of "Dual Slot : On/Off" to "DC Direct M:" when using the DCDM switch hotkey.
  - Now SMS Prompt works properly, unlike on official firmware.
  - Invoking the spectrum from a Zone will scan the zone instead, with no capture/block features.
    - You can press the Side 2 key to skip the current received channel.
    - Switch to VFO or Channel mode if you want the regular spectrum.
  - Talker Alias is now supported:
    - Enable via Extra -> Talker Alias.
    - You can also toggle Talker Alias on and off with the * key during a DMR call, but this change is not automatically saved. It gets saved the next time any other setting is saved.
    - Talker Alias received with accents and fancy characters are untested and may not display properly. At the same time, you will see weird characters as the DMR firmware sometimes mangles Talker Alias frames.
  - As a result of Talker Alias, "Called Show" menu is gone. If you want the old behaviour, stick to Beta 40 or official firmware.
  - When DMR firmware produces invalid IDs, errors will now display on screen.
    - This is the new UX for the old ID=275 problem until Radtel/iRadio gets the DMR fixed.
    - If you have Talker Alias enabled, you may be able to see who's calling if the data is available.
  - If you made it this far, I'm impressed, you get to know about the proper upgrade path from Beta 40 to Beta 41:
    - Your RT-4D must be either at either Beta 40 or Official v3.16 earlier firmwares. If you're not, you're your own and need to do a new codeplug from scratch.
    - Flash Beta 41.
    - Using [Joel's CPS](https://github.com/jcalado/rt4d-cps), read the codeplug from the RT-4D.
    - Write the codeplug back, ensuring you ticked the "Beta 41" option in the write screen.
    - Enjoy

# Screenshot tool

If you use the -screenshot.bin firmware, you can use the screenshot binary with [Joel's handy tool](https://github.com/jcalado/radshot). Note that taking screenshots will affect the radio's performance and may lead to eventually hangs or weird behaviours.

# Flashing tools

* [Flasher CLI](https://github.com/DualTachyon/radtel-rt-4d-flasher-cli) - Windows CLI (and Linux if you have Mono and build yourself)
* [rt890-flash-rs](https://github.com/bricky149/rt890-flash-rs/releases/) - Windows and Linux CLI
* [RT-4D_Flasher](https://github.com/omegatee/RT-4D_Flasher) - Linux GUI
* [RT-4D Web Flasher](https://thankful-water-0753da603.6.azurestaticapps.net/) - Web based

# Beta 40 and earlier

Beta 40 and earlier history has been shelved. If you want to go back to any of it, you can do so [here](https://github.com/DualTachyon/rt-4d-fw-beta/tree/the-past).

