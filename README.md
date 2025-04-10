# Support

* If you like my work, you can support me through https://ko-fi.com/DualTachyon

# Beta test build of the fully reverse engineered version of RT-4D v3.14 firmware.

The RT-4D v3.14 firmware has been fully reverse engineered and before it can be improved with better features and better user experience, I need help in testing the base firmware.
The build in this repository has feature parity with Radtel's original firmware, but probably has some bugs.
Since there is a lot of code and a lot of ways to trigger every feature/quirk of the firmware, I was not able to test everything.

# DISCLAIMER

While efforts have been made to avoid bugs that could corrupt your SPI flash, IT IS IMPERATIVE THAT USERS MAKE A BACKUP OF IT.

# SPI flash backup

The following tools can be used:
* [RT-4D-SPIFlash-CLI](https://github.com/DualTachyon/rt-4d-spiflash-cli)
* [rt890-flash-rs](https://github.com/bricky149/rt890-flash-rs/releases/tag/1.2.96)

How to make a backup:

```
Windows: RT-4D-SPIFlash-CLI.exe -p COMx -r spi.backup
Windows: rt890-flash-rs.exe -4d -p COMx -o spi.backup
Linux: ./rt890-flash-rs -4d -p /dev/ttyUSBx -o spi.backup
```

KEEP THIS BACKUP SAFE SOMEWHERE. It will allow you to recover your SPI flash to a fully working state, no matter what happens to it.

# Requirements

* You must have DMR firmware 1.2.0.6 installed on your RT-4D. 1.2.0.3 may work, but anyone reporting bugs with any older versions will be blocked from this repository.
* Do not request new features or changes, this repository is strictly for testing the reverse engineered firmware against the original. Doing so will get you blocked.
* If you finds bugs, report them on the Issues tab here on GitHub. Make a proper detailed bug report. Reporting your bugs to me on Telegram is a good way to get blocked and ignored.

A good bug report is: "XYZ feature doesn't work. I tested it by doing ABC and used DEF settings. You can see in this video/photo that original firmware works, but not in your beta build".
Also a good report: "The text/bitmap in ABC is corrupted/misaligned/missing when doing DEF".

A bad bug report is: "XYZ doesn't work, plz fix it" and will get you blocked.

# What's different from the original firmware

* If you fitted a 64MBytes SPI flash on your RT-4D, DO NOT USE THIS BUILD. I don't have that type of flash so I couldn't test the new driver for it and didn't want to include it yet.
* Some typos have been fixed.
* A bug that affects address book lookup has been fixed (whether correctly is a different story).
* The Talkaround and Reverse icons match the popup display. In the original, they are reversed.
* DMR screen shows a different UI when Promiscuous is enabled. It is a small taster of what is to come after the current firmware is fully tested.
 * As a result of this change, it is possible the non-promiscuous UI is (slightly) broken. So please go easy on reporting bugs in non-promiscuous mode.
 * The text for Individual/Group/All calls has been shortened to just Private/Group/All to fit with the new UI mode and affects the old UI mode too.

# How to flash the beta build

You can use the many firmware flashing tools:

* [rt890-flash-rs](https://github.com/bricky149/rt890-flash-rs/releases/tag/1.2.96)
* [RT-4D_Flasher](https://github.com/omegatee/RT-4D_Flasher)
* [RT-4D-python-flasher](https://github.com/fagci/RT-4D-python-flasher)
* [rt4d-goflasher](https://github.com/fagci/rt4d-goflasher)

